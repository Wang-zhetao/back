<template>
 <Layout class-prefix="layout">
    <NumberPad/>
    <Types :xxx="hi"/>
    <Notes/>
    <Tags/>
  </Layout>
</template>

<script lang="ts">
import NumberPad from '@/components/Money/NumberPad.vue';
import Types from '@/components/Money/Types.vue';
import Notes from '@/components/Money/Notes.vue';
import Tags from '@/components/Money/Tags.vue';
  export default {
    components: { NumberPad, Types, Notes, Tags }
}
</script>

<style lang="scss">
  .layout-content {
    display: flex;
    flex-direction: column-reverse;
  }
</style>

