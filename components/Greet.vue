<template>
  <UForm :schema="formSchema" :state="state" @submit="onSubmit">
    <UFormGroup label="Name" name="name" class="mb-3">
      <UInput v-model="state.name" placeholder="Enter a name..." />
    </UFormGroup>

    <UButton type="submit">Greet</UButton>
  </UForm>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { z } from "zod";
import { invoke } from "@tauri-apps/api/core";

const toast = useToast();

const formSchema = z.object({
  name: z.string().nonempty(),
});
type Form = z.infer<typeof formSchema>;

const state = ref<Form>({ name: "" });

async function onSubmit() {
  // Learn more about Tauri commands at https://tauri.app/v1/guides/features/command
  const response = await invoke("greet", { name: state.value.name }) as string;

  toast.add({
    title: "Greetings!",
    description: response
  });
}
</script>
