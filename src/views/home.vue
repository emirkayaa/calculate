<template>
    <div class="app">
        <div class="container bg-dark text-light" style="height:100vh">
            <div class="d-flex justify-content-center align-items-center h-100">
                <div class="calculate-wrapper p-3">
                    <div>
                        <span class="fs-3">Calculate</span>
                    </div>
                    <div class="mt-2  p-2">
                        <input type="number" class="text-end">
                    </div>
                    <div class="row">
                        <div class="col-4">
                            <button class="text-light p-2">AC</button>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
}
</script>

<style>
.calculate-wrapper {
    border: 1px solid white;
    border-radius: 10px;
}

input {
    border: 0
}

button {
    background: slategray;

}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
}
</style>