<script setup lang="ts">
import AppHeader from "~/components/AppHeader.vue";
import AppFooter from "~/components/AppFooter.vue";
</script>

<template>
  <div>
    <AppHeader />
    <main class="content-wrapper overflow-y-auto">
      <slot />
    </main>
    <AppFooter />
    <ClientOnly>
      <div
          v-if="$pwa?.offlineReady || $pwa?.needRefresh"
          class="pwa-toast"
          role="alert"
      >
        <div class="message">
          <span v-if="$pwa.offlineReady">
            App ready to work offline
          </span>
          <span v-else>
            New content available, click on reload button to update.
          </span>
        </div>
        <button
            v-if="$pwa.needRefresh"
            @click="$pwa.updateServiceWorker()"
        >
          Reload
        </button>
        <button @click="$pwa.cancelPrompt()">
          Close
        </button>
      </div>
      <div
          v-if="$pwa?.showInstallPrompt && !$pwa?.offlineReady && !$pwa?.needRefresh"
          class="pwa-toast"
          role="alert"
      >
        <div class="message">
          <span>
            Install PWA
          </span>
        </div>
        <button @click="$pwa.install()">
          Install
        </button>
        <button @click="$pwa.cancelInstall()">
          Cancel
        </button>
      </div>
    </ClientOnly>
  </div>
</template>


<style scoped>
.content-wrapper {
  min-height: calc(100vh - (60px + 80px));
  margin-top: 60px;
  margin-bottom: 80px;
}

.pwa-toast {
  position: fixed;
  right: 0;
  bottom: 0;
  margin: 16px;
  padding: 12px;
  border: 1px solid #8885;
  border-radius: 4px;
  z-index: 1;
  text-align: left;
  box-shadow: 3px 4px 5px 0 #8885;
}
.pwa-toast .message {
  margin-bottom: 8px;
}
.pwa-toast button {
  border: 1px solid #8885;
  outline: none;
  margin-right: 5px;
  border-radius: 2px;
  padding: 3px 10px;
}
</style>