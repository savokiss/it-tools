<script setup lang="ts">
const { availableLocales, locale } = useI18n();

const localesLong: Record<string, string> = {
  en: 'English',
  zh: '中文',
  ja: '日本語',
  es: 'Español',
  fr: 'Français',
  pt: 'Português',
  ru: 'Русский',
  de: 'Deutsch',
  hi: 'हिन्दी',
};

const localeOptions = computed(() =>
  availableLocales.map(locale => ({
    label: localesLong[locale] ?? locale,
    value: locale,
  })),
);
</script>

<template>
  <c-select
    v-model:value="locale"
    :options="localeOptions"
    placeholder="Select a language"
    w-100px
  />
</template>
