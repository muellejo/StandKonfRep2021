<template>
  <div>
    <div class="container mx-auto px-8 lg:px-48">
      <div class="pb-16">
        <div class="mb-4 text-2xl font-bold">{{ $t('message') }}</div>
        <p>{{ $t('titleText')}}</p>
      </div>
      <div class="mx-auto pt-8 pb-6 md:flex md:justify-between items-end border-b-2 border-gray-300">
        <div class="text-2xl mb-4 md:mb-0">{{ $t('productArea') }}</div>
      </div>
      <div class="mx-auto py-8 md:flex md:justify-between md:flex-wrap">
        <selectable-plan
          id="1">
        </selectable-plan>
        <selectable-plan
          id="2">
        </selectable-plan>
      </div>
    </div>
  </div>
</template>

<script>
import SelectablePlan from '@/components/SelectablePlan.vue'

export default {
  components: {
    SelectablePlan
  },
  methods: {
    setName(productName) {
      var planName = productName
      return planName 
    }
  }
}
</script>