<script setup lang="ts">
import { Head, Link } from '@inertiajs/vue3'
import DashboardLayout from '@/Layouts/DashboardLayout.vue'
import { User } from '@/types';
import { SquareUserIcon, UsersIcon } from 'lucide-vue-next';

const props = defineProps<{
    user: User;
}>();

</script>

<template>

    <Head>
        <title>Dashboard Admin</title>
    </Head>

    <DashboardLayout>
        <template #header>
            <h1 class="text-xl font-semibold tracking-tight">Dashboard Admin</h1>
        </template>

        <section class="bg-white p-3 rounded-lg mb-3 dark:bg-neutral-800">
            <div class="mb-3">
                <p class="font-semibold text-2xl tracking-tight">Selamat Datang, {{ props?.user?.name ?? 'Kamu' }}</p>
                <p class="text-sm text-neutral-500 dark:text-neutral-400">Kamu dapat langsung memilih 3 menu dibawah.</p>
            </div>
        </section>

        <section class="grid gap-2 grid-cols-2">
            <Link :href="route('admin.users.index')"
                class="bg-white border border-neutral-300 rounded-lg p-3 hover:border-green-500 dark:bg-neutral-800 dark:border-neutral-600 dark:hover:border-green-600">
            <UsersIcon :size="32" class="mb-3" />
            <p class="font-semibold tracking-tight text-lg sm:text-xl">Daftar Akun</p>
            </Link>
            <Link :href="route('profile.edit')"
                class="bg-white border border-neutral-300 rounded-lg p-3 hover:border-green-500 dark:bg-neutral-800 dark:border-neutral-600 dark:hover:border-green-600">
            <SquareUserIcon :size="32" class="mb-3" />
            <p class="font-semibold tracking-tight text-lg sm:text-xl">Profile</p>
            </Link>
        </section>
    </DashboardLayout>
</template>
