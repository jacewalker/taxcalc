<script>
    export default {
    data() {
        return {
        salary: undefined,
        grossIncome: self.salary,
            isData: true
        }
    },
    methods: {
        calculateGross(x) {
            if (x > 0 && x <= 18200) {
                return Math.round(x)
            } else if (x >= 18201 && x <= 45000) {
                let tax = (x - 18200) * 0.19
                return Math.round(x - tax)
            } else if (x >= 45001 && x <= 120000) {
                let tax = (x - 45000) * 0.325
                return Math.round(x - tax - 5092)
            } else if (x >= 120001 && x <= 180000) {
                let tax = (x - 120000) * 0.37
                return Math.round(x - tax - 29467)
            } else if (x >= 180001) {
                let tax = (x - 180000) * 0.45
                return Math.round(x - tax - 51667)
            }
        }
    }
    }
</script>



<template>

    <form>
    <div class="mb-3">
        <input type="text" class="form-control" id="salaryBox" placeholder="Enter your salary..." v-model="salary" >
        <div id="salaryHelp" class="form-text">We'll never share your information with anyone else.</div>
    </div>
    <div class="mb-3">
        <label class="form-label"> Your Net Income is:  {{ calculateGross(salary) }}</label>
    </div>
    <button @click="calculateGross()" class="btn btn-secondary">Submit</button>
    </form>

</template>

<style scoped>
    #salaryBox {
        width: 500px;
        text-align: center;
    }

    form {
        display: inline-block;
    }
</style>


