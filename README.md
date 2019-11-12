# vue-online-offline

Vue Component with online/offline slots

## Project setup
```
yarn install vue-online-offline
```

## Usage

```vue
<template>
  <vue-online-offline @online="isOnline" @offline="isOffline">
    <div slot="online">I'm online! 🎉</div>
    <div slot="offline">I'm offline. 🤨</div>
  </vue-online-offline>
</template>

<script>
import VueOnlineOffline from 'vue-online-offline

export default {
  components: { VueOnlineOffline },
  methods: {
    isOnline() {
      console.log(`Now I'm online!`)
    },
    isOffline() {
      console.log(`Now I'm offline.`)
    }
  }
}
</script>
```