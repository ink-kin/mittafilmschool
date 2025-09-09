<script setup lang="ts">
const columns = [{
  label: 'Курсы',
  children: [{
    label: 'Режиссёрская мастерская', to:'https://seminar.mitta.ru/rejissura'
  }, {
    label: 'Сценарная мастерская', to: 'http://seminar.mitta.ru/scenarist'
  }, {
    label: 'Операторская мастерская', to: 'http://dp.mitta.ru/'
  }, {
    label: 'Продюсерская мастерская', to: 'http://producers.mitta.ru/'
  }, {
    label: 'Актерская мастерская', to: 'http://akter.mitta.ru/'
  }]
}, {
  label: 'Услуги',
  children: [{
    label: 'Обучить', to: 'https://mitta.ru/kinokursy'
  }, {
    label: 'Снять фильм', to: 'https://mitta.ru/o-kinoshkole/nashi-prepodavateli'
  }, {
    label: 'Подобрать людей', to: 'https://mitta.ru'
  }, {
    label: 'Найти спонсоров', to: 'https://mitta.ru/o-kinoshkole/premium/klub-kinoshkoly'
  }, {
    label: 'Аренда оборудования', to: 'https://mitta.ru/o-kinoshkole/tekhnicheskaya-baza'
  }]
}, {
  label: 'Компания',
  children: [{
    label: 'О нас', to: 'https://mitta.ru/'
  }, {
    label: 'Цены', to: '#pricing'
  }, {
    label: 'Работа у нас', to: 'https://mitta.ru/'
  }, {
    label: 'Блог', to: 'https://t.me/mittafilmschool'
  }, {
    label: 'Архив', to: '/arhiv'
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
