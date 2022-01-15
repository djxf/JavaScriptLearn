<template>
    <h1>2022.01.15</h1>
    <button @click="sum(1, 2)">function</button>
</template>


<script>
export default {
    data: {
        data1: [
            {name: "Zachary", age: 28},
            {name: "Nicholas", age: 29}, 
        ]
    },
    methods: {
        regexpTest() {
            // var patternal = '/at/g';
            // var pattern2 = '/[bc]at/i';
            // var pattern3 = '/.at/gi';

            // var pattern4  = new RegExp("[bc]at", "i");
            
        },

        // Function类型
        sum (num1, num2) {
            this.data1.sort(this.createComparisonFunction("name"))
            alert(data1[0].name)

            this.data1.sort(this.createComparisonFunction("age"))
            alert(data1[0].name)
        },
        createComparisonFunction(propertyName) {
            return function(object1, object2) {
                var value1 = object1[propertyName];
                var value2 = object2[propertyName];
                if (value1 < value2) {
                    return -1;
                } else if (value1 > value2) {
                    return 1;
                } else {
                    return 0;
                }
            }
        }
    }
}
</script>