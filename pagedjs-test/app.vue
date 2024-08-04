<template>
  <div class="wrapper" style="display: flex; overflow: hidden; width: 100vw; height: 100vh">
    <aside
      class="sidebar"
      style="
        width: 25vh;
        display: flex;
        flex-direction: column;
        gap: 1rem;
        border-right: 1px solid black;
        height: 100%;
        flex: 1;
        padding: 1rem;
      "
    >
      <div><h2>Ich bin die Sidebar</h2></div>
      <p>ich mach so dies und das</p>

      <div style="display: flex; flex-direction: column; gap: 1rem">
        <button @click="handlePrint">Drucken</button>
      </div>
    </aside>

    <main class="main-content" style="flex: 3; display: flex; flex-direction: column; overflow: auto">
      <PrintView ref="printViewRef" />
    </main>
  </div>
</template>

<script setup lang="ts">
import { PrintView } from "#components";
// import { Previewer } from "pagedjs";

// onMounted(() => {
//   let paged = new Previewer();
//   let flow = paged.preview(contentRef.value, undefined, document.body).then((flow) => {
//     console.log("Rendered", flow.total, "pages.");
//   });
// });

const printViewRef = ref<InstanceType<typeof PrintView>>();

const handlePrint = () => {
  if (!printViewRef.value) return;

  printViewRef.value.handlePrint();
};
</script>

<style>
body {
  padding: 0;
  margin: 0;
}

/* @page {
  size: 148mm 210mm;
  margin-top: 10mm;
  margin-right: 20mm;
  margin-bottom: 25mm;
  margin-left: 15mm;

  @bottom-left {
    content: counter(page);
  }

  @bottom-center {
    content: string(title);
    text-transform: uppercase;
  }
} */
</style>
