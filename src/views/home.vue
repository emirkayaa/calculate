<template>
    <div class="app">
        <div class="container bg-dark text-light" style="height:100vh">
            <div class="d-flex justify-content-center align-items-center h-100">
                <div class="calculate-wrapper px-2 py-3">
                    <div>
                        <span class="fs-1 fw-bold">Calculate</span>
                    </div>
                    <div class="mt-2 p-2 d-flex justify-content-end">
                        <div class="w-100 m-1 p-3 text-end fw-bold text-white rounded bg-vue-dark fs-3">{{ sum
                        }}</div>
                    </div>
                    <div class="row justify-content-end">
                        <div class="col-3" v-for="e in calculatorElement" :key=e>
                            <div class="text-light text-center m-1 py-3 bg-vue-dark rounded hover-class" style="width:50px"
                                :class="{ 'bg-vue-green': ['AC', '*', '/', ',', '-', '+', '%', '='].includes(e) }"
                                @click="islem(e)">
                                {{ e }}
                            </div>
                        </div>
                    </div>


                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            sum: ' ',
            calculatorElement: ['AC', '*', '/', '-', 7, 8, 9, '+', 4, 5, 6, '%', 1, 2, 3, '=', 0, ','],
            operator: null,
            pervius: '',
        }
    },
    methods: {
        islem(e) {
            if (!isNaN(e) || e === '.') {
                this.sum += e + '';
            }
            if (e === 'AC') {
                this.sum = ' '
            }
            if (e === '%') {
                this.sum = this.sum / 100 + ''
            }
            if (['*', '/', '-', '+'].includes(e)) {
                this.operator = e;
                this.previus = this.sum;
                this.sum = '';
            }
            if (e === '=') {
                this.sum = eval(this.previus + this.operator + this.sum);
                this.previus = '';
                this.operator = null
            }

        }
    },
}
</script>

<style>
.calculate-wrapper {
    background: #213041;
    max-width: 300px;
    border-radius: 25px;
}

input {
    border: 0;
    height: 30px;
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
}

.bg-vue-dark {
    background: #31475e;
    font-size: 20px;
}

.hover-class:hover {
    cursor: pointer;
    background: #3d5875;
}

.bg-vue-green {
    background: #3fb984;
}
</style>