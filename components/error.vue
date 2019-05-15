<template lang="pug">
.wrapper
  .flex.justify-center.items-center
    .logo
      img(src="/images/error.png")
    .error-group
      .header This site can't be reached
      .description {{ domain }}.{{ tld }}'s server IP address could not be found.
      ul.list-reset.suggestions
        li Did you mean {{ domain }}.{{ tld }}
        li Search Noodle for {{ domain }}
      .error ERR_NAME_NOT_RESOLVED
</template>

<script>
export default {
  name: 'Error',
  props: {
    domain: {
      type: String,
      default: 'domain'
    },
    tld: {
      type: String,
      default: 'tld'
    }
  },
  data() {
    return {}
  }
}
</script>

<style lang="postCss">
.logo {
  height: 128px;
  width: 128px;
}
.wrapper {
  height: 100vh;
  @apply .flex .justify-center .items-center
}
.error-group {
  height: 12em;
  width: 50vw;
  @apply .ml-8
}
.header {
  @apply .text-grey .text-5xl .py-2
}
.description {
  @apply .text-grey .text-3xl .py-2
}
.suggestions {
  @apply .text-grey .text-lg .py-2
}
.error {
  @apply .text-grey .text-xl .py-2
}
</style>
