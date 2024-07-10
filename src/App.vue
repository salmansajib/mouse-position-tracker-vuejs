<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const clientx = ref(0);
const clienty = ref(0);
const pagex = ref(0);
const pagey = ref(0);
const offsetx = ref(0);
const offsety = ref(0);
const layerx = ref(0);
const layery = ref(0);
const screenx = ref(0);
const screeny = ref(0);

function updateValue(event) {
  clientx.value = event.clientX;
  clienty.value = event.clientY;
  pagex.value = event.pageX;
  pagey.value = event.pageY;
  offsetx.value = event.offsetX;
  offsety.value = event.offsetY;

  // console.log(event);
}

onMounted(() => window.addEventListener("mousemove", updateValue));
onUnmounted(() => window.removeEventListener("mousemove", updateValue));
</script>

<template>
  <div class="bg-zinc-950 text-gray-100 min-h-dvh">
    <header class="min-h-[11vh]">
      <h1
        class="text-3xl md:text-5xl font-semibold w-max mx-auto text-center pt-5"
      >
        Track Your Mouse
      </h1>
    </header>

    <main
      class="min-h-[91vh] flex flex-col gap-5 items-center justify-center pb-5"
    >
      <div
        class="flex items-center justify-center gap-5 bg-green-400 text-zinc-900 w-[350px] h-[100px] rounded"
      >
        <p class="text-2xl font-bold">Client Position X</p>
        <p
          class="font-semibold text-3xl text-purple-400 bg-slate-950 w-[100px] h-[50px] rounded flex items-center justify-center"
        >
          {{ clientx }}
        </p>
      </div>
      <div
        class="flex items-center justify-center gap-5 bg-green-400 text-zinc-900 w-[350px] h-[100px] rounded"
      >
        <p class="text-2xl font-bold">Client Position Y</p>
        <p
          class="font-semibold text-3xl text-purple-400 bg-slate-950 w-[100px] h-[50px] rounded flex items-center justify-center"
        >
          {{ clienty }}
        </p>
      </div>
      <div
        class="flex items-center justify-center gap-5 bg-green-400 text-zinc-900 w-[350px] h-[100px] rounded"
      >
        <p class="text-2xl font-bold">Page Position X</p>
        <p
          class="font-semibold text-3xl text-purple-400 bg-slate-950 w-[100px] h-[50px] rounded flex items-center justify-center"
        >
          {{ pagex }}
        </p>
      </div>
      <div
        class="flex items-center justify-center gap-5 bg-green-400 text-zinc-900 w-[350px] h-[100px] rounded"
      >
        <p class="text-2xl font-bold">Page Position Y</p>
        <p
          class="font-semibold text-3xl text-purple-400 bg-slate-950 w-[100px] h-[50px] rounded flex items-center justify-center"
        >
          {{ pagey }}
        </p>
      </div>
      <div
        class="flex items-center justify-center gap-5 bg-green-400 text-zinc-900 w-[350px] h-[100px] rounded"
      >
        <p class="text-2xl font-bold">Offset Position X</p>
        <p
          class="font-semibold text-3xl text-purple-400 bg-slate-950 w-[100px] h-[50px] rounded flex items-center justify-center"
        >
          {{ offsetx }}
        </p>
      </div>
      <div
        class="flex items-center justify-center gap-5 bg-green-400 text-zinc-900 w-[350px] h-[100px] rounded"
      >
        <p class="text-2xl font-bold">Offset Position Y</p>
        <p
          class="font-semibold text-3xl text-purple-400 bg-slate-950 w-[100px] h-[50px] rounded flex items-center justify-center"
        >
          {{ offsety }}
        </p>
      </div>
    </main>
  </div>
</template>
