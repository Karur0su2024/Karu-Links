<script setup>
// Importování komponent a nástrojů
// - AuthenticatedLayout je layout, který se používá pro přihlášené uživatele, zajišťuje konzistentní vzhled stránky
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
// - Head komponenta z Inertia.js používaná pro nastavení titulku stránky v prohlížeči
import { Head } from '@inertiajs/vue3';
</script>

<template>
    <!-- Nastavení titulku stránky na "Dashboard" -->
    <Head title="Dashboard" />

    <!-- Použití layoutu pro autentizované uživatele jako hlavní obal stránky -->
    <AuthenticatedLayout>
        <!-- Slot pro záhlaví stránky -->
        <template #header>
            <!-- Nadpis stránky s formátováním -->
            <h2
                class="text-xl font-semibold leading-tight text-gray-800"
            >
                Dashboard
            </h2>
        </template>

        <!-- Hlavní obsah stránky s odsazením -->
        <div class="py-12">
            <!-- Centrovaný kontejner s maximální šířkou a responzivním paddingem -->
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
                <!-- Karta se stínem a zaoblenými rohy na větších obrazovkách -->
                <div
                    class="overflow-hidden bg-white shadow-sm sm:rounded-lg"
                >
                    <!-- Vnitřní obsah karty s paddingem a barvou textu -->
                    <div class="p-6 text-gray-900">
                        You're logged in!
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
