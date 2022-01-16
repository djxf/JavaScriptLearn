<template>
    <h1>面向对象的程序设计20220116</h1>
</template>


<script>
export default {
    methods: {
        test1() {
            var person = new Object();
            person.name = "Nicholas"
            person.age = 29;
            person.job = "Software Engineer";

            person.sayName = function() {
                alert(this.name);
            }
        }, 
        test2() {
            //属性类型
            var person = {};
            Object.defineProperties(person, "name", {
                writable: false,
                value: "Nicholas"
            })

            var book = {
                _year: 2004,
                edition:1
            }
            
            Object.defineProperty(
                book, "year", {
                    get: function() {
                        return this._year;
                    },
                    set: function(newValue) {
                        if (newValue > 2004) {
                            this._year += newValue;
                            this.edition += newValue - 2004;
                        }
                    }
                }
            )
        },
        //工厂模式：抽象了创建对象的过程。
        createPerson(name, age, job) {
            var o = new Object();
            o.name = name;
            o.age = age;
            o.job = job;
            o.sayName = function() {
                alert(this.name)
            }
        }
    }
}
</script>