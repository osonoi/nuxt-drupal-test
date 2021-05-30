<template>
  <div
    class="bg-teal-100 border-t-4 border-teal-500 rounded-b text-teal-900 shadow-md mb-5"
  >

      <time class="text-gray-700 text-base mb-1 block md:w-1/6">
        {{ title }}
      </time>
      <div class="md:w-10/12">
        {{ body }}
      </div>
      <div class="md:w-10/12">
        {{ recipe }}
      </div>
    </a>
  </div>
</template>

<script>
export default {
  name: 'LayoutInformationList',
  props: {
    title: {
      type: String,
      required: true,
    },
    body: {
      type: String,
      required: true,
    },
    recipe: {
      type: String,
      required: true,
    },
    id: {
      type: String,
      required: true,
    },
  },
}
</script>
