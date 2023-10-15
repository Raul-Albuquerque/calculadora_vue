<script setup>
    const props = defineProps(['realizarOperacao', 'getNumber1', 'getNumber2', 'getOperation', 'getResultado'])
</script>

<template>
    <form class="mt-3 bg-dark p-4 rounded-4">
        <div class="row d-flex justify-content-center align-items-center">
            <div class="col-md-2">
                <input @change="props.realizarOperacao" @keyup="props.getNumber1"
                    class="form-control" type="number" required placeholder="Digite um número">
            </div>
            <div class="col-md-1">
                <select @change="props.getOperation" @focusout="props.realizarOperacao"
                    class="form-control text-center fw-bold operation">
                    <option value="+">+</option>
                    <option value="-">-</option>
                    <option value="*">*</option>
                    <option value="/">/</option>
                </select>
            </div>
            <div class="col-md-2">
                <input @change="props.realizarOperacao" @keyup="props.getNumber2"
                    class="form-control" type="number" required placeholder="Digite outro número">
            </div>
            <div class="col-md-1 text-light ms-5">
                <h6 class="fw-bold">=</h6>
            </div>
            <div class="col-md-2 bg-light rounded-2 text-center result">
                {{ props.getResultado }}
            </div>
        </div>
    </form>
</template>
<style scoped>
    .operation {
        cursor: pointer;
    }

    .result {
        height: 37px;
        padding: 6px 12px;
    }
</style>