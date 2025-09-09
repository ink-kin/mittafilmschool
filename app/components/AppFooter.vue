<script setup lang="ts">
const columns = [{
  label: 'Курсы',
  children: [{
    label: 'Режиссёрская мастерская'
  }, {
    label: 'Сценарная мастерская'
  }, {
    label: 'Операторская мастерская'
  }, {
    label: 'Продюсерская мастерская'
  }, {
    label: 'Актерская мастерская'
  }]
}, {
  label: 'Услуги',
  children: [{
    label: 'Обучить'
  }, {
    label: 'Снять фильм'
  }, {
    label: 'Подобрать людей'
  }, {
    label: 'Найти спонсоров'
  }, {
    label: 'Аренда оборудования'
  }]
}, {
  label: 'Компания',
  children: [{
    label: 'О нас'
  }, {
    label: 'Цены'
  }, {
    label: 'Работа у нас'
  }, {
    label: 'Блог'
  }]
}]

const toast = useToast()

const email = ref('')
const loading = ref(false)

function onSubmit() {
  loading.value = true

  toast.add({
    title: 'Подпишитесь',
    description: 'Подпишись на рассылку новостей!'
  })
}
</script>

<template>
  <USeparator
    icon="i-simple-icons-nuxtdotjs"
    class="h-px"
  />

  <UFooter :ui="{ top: 'border-b border-default' }">
    <template #top>
      <UContainer>
        <UFooterColumns :columns="columns">
          <template #right>
            <form @submit.prevent="onSubmit">
              <UFormField
                name="email"
                label="Subscribe to our newsletter"
                size="lg"
              >
                <UInput
                  v-model="email"
                  type="email"
                  class="w-full"
                  placeholder="Enter your email"
                >
                  <template #trailing>
                    <UButton
                      type="submit"
                      size="xs"
                      label="Subscribe"
                    />
                  </template>
                </UInput>
              </UFormField>
            </form>
          </template>
        </UFooterColumns>
      </UContainer>
    </template>

    <template #left>
      <p class="text-sm text-muted">
        Built by ILya N KLishin with Nuxt UI • © {{ new Date().getFullYear() }}
      </p>
    </template>

    <template #right>
      <UButton
        to="https://t.me/mittafilmschool"
        target="_blank"
        icon="i-simple-icons-discord"
        aria-label="Nuxt on Discord"
        color="neutral"
        variant="ghost"
      />
      <UButton
        to="https://vk.com/mitta_film_school"
        target="_blank"
        icon="i-simple-icons-x"
        aria-label="Nuxt on X"
        color="neutral"
        variant="ghost"
      />
      <UButton
        to="https://github.com/ink-kin/mittafilmschool"
        target="_blank"
        icon="i-simple-icons-github"
        aria-label="Nuxt UI on GitHub"
        color="neutral"
        variant="ghost"
      />
    </template>
  </UFooter>
</template>
