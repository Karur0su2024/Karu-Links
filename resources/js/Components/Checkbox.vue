<script setup>
// Importuje funkci computed z Vue, která slouží k vytváření reaktivních vypočítaných hodnot
import { computed } from 'vue';

// Definice událostí, které komponenta může emitovat
// 'update:checked' událost je emitována, když se změní stav checkboxu
const emit = defineEmits(['update:checked']);

// Definice vlastností (props), které komponenta přijímá
const props = defineProps({
    // Vlastnost 'checked' určuje, zda je checkbox zaškrtnutý
    // Může být buď boolean (true/false) nebo pole (pro skupiny checkboxů)
    // Je povinná (required: true)
    checked: {
        type: [Array, Boolean],
        required: true,
    },
    // Vlastnost 'value' určuje hodnotu checkboxu
    // Je volitelná a má výchozí hodnotu null
    value: {
        default: null,
    },
});

// Vytvoření computed property (vypočítané vlastnosti) pro obousměrnou vazbu (v-model)
const proxyChecked = computed({
    // Getter - vrací aktuální hodnotu 'checked' z props
    get() {
        return props.checked;
    },

    // Setter - když se hodnota změní, emituje událost 'update:checked' s novou hodnotou
    // Toto umožňuje rodičovské komponentě aktualizovat svůj stav
    set(val) {
        emit('update:checked', val);
    },
});
</script>

<template>
    <input
        type="checkbox"
        :value="value"
        v-model="proxyChecked"
        class="rounded border-gray-300 text-indigo-600 shadow-sm focus:ring-indigo-500" <!-- Tailwind CSS třídy pro styling -->
    />
</template>


<!-- Nastaví hodnotu checkboxu z props 'value' -->

<!-- Obousměrná vazba na vypočtenou vlastnost -->
