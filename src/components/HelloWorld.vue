<template>
<div id="may_tinh">
    <div id="ket_qua">
        <div style="    position: absolute;
    top: 0;" class="hien_so">
          <p>{{showNumber}}</p>
        </div>
        <div id="ket_qua_cu">
            <input type="text" :value="inputValue">
        </div>
    </div>
    <div id="ban_phim">
        <div id="ban_phim">
            <button class="he_thong" @click="clear()" id="xoa_tat_ca">C</button>
            <button class="he_thong" @click="heThongXoa()" id="xoa_tung_so">CE</button>
            <button class="he_thong" @click="heThongPhan()" id="%">%</button>
            <button class="he_thong" @click="heThongChia()" id="/">÷</button>
            <button class="con_so" @click="number7()" id="7">7</button>
            <button class="con_so" @click="number8()" id="8">8</button>
            <button class="con_so" @click="number9()" id="9">9</button>
            <button class="he_thong" @click="heThongNhan()" id="*">×</button>
            <button class="con_so" @click="number4()" id="4">4</button>
            <button class="con_so" @click="number5()" id="5">5</button>
            <button class="con_so" @click="number6()" id="6">6</button>
            <button class="he_thong" @click="heThongTru()" id="-">-</button>
            <button class="con_so" @click="number1()" id="1">1</button>
            <button class="con_so" @click="number2()" id="2">2</button>
            <button class="con_so" @click="number3()" id="3">3</button>
            <button class="he_thong" @click="hetThongCong()" id="+">+</button>
            <button class="trong" id="trong"></button>
            <button class="con_so" @click="number0()" id="0">0</button>
            <button class="trong" id="trong"></button>
            <button class="he_thong" @click="tinh()" id="=">=</button>
        </div>
    </div>

</div>
</template>

<script>
import stringCalculator from 'string-calculator'
export default {
    name: 'HelloWorld',
    data() {
        return {
            total: [],
            inputValue: 0,
        }
    },
    methods: {
        number0() {
            this.total.push(0)
            this.inputValue = 0
            console.log(this.total)
        },
        number1() {
            this.total.push(1)
            this.inputValue = 1

            console.log(this.total)
        },
        number2() {
            this.total.push(2)
            this.inputValue = 2

            console.log(this.total)
        },
        number3() {
            this.total.push(3)
            this.inputValue = 3

            console.log(this.total)
        },
        number4() {
            this.total.push(4)
            this.inputValue = 4

            console.log(this.total)
        },
        number5() {
            this.total.push(5)
            this.inputValue = 5

            console.log(this.total)
        },
        number6() {
            this.total.push(6)
            this.inputValue = 6

            console.log(this.total)
        },
        number7() {
            this.total.push(7)
            this.inputValue = 7

            console.log(this.total)
        },
        number8() {
            this.total.push(8)
            this.inputValue = 8

            console.log(this.total)
        },
        number9() {
            this.total.push(9)
            this.inputValue = 9

            console.log(this.total)
        },
        hetThongCong() {
            this.total.push('+')
            console.log(this.total)
        },
        heThongTru() {
            this.total.push('-')
            console.log(this.total)
        },
        heThongNhan() {
            this.total.push('*')
            console.log(this.total)
        },
        heThongChia() {
            this.total.push('/')
            console.log(this.total)
        },
        clear() {
            this.total = []
            this.inputValue = 0
            console.log(this.total)
        },
        tinh() {
            var result = stringCalculator(this.total.join(''))
            this.inputValue = result
            console.log(this.inputValue)
        },
        heThongXoa() {
          this.total.pop()
        
        }
    },
    computed: {
      showNumber() {
        return this.total.map(x => x).join("")
      }
    }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
#ket_qua {
    display: flex;
    align-items: center;
    justify-content: center;
}

input {
    padding: 10px;
    border: none;
    box-shadow: 0 0 5px #ccc;
    border-radius: 10px;
    padding: 16px 20px;
    font-size: 16px;
    font-weight: 700;
}

.he_thong,
.con_so,
.trong {
    width: 50px;
    height: 50px;
    margin: 15px;
    float: left;
    border-radius: 50%;
    border-width: 0;
    font-weight: bold;
    font-size: 16px;
}

.con_so,
.trong {
    background-color: #eaedef;
}

.he_thong,
.con_so {
    cursor: pointer;
}

.he_thong:active,
.con_so:active {
    font-size: 13px;
}

.he_thong:focus,
.con_so:focus,
.trong:focus {
    outline: 0;
}

button:nth-child(4) {
    font-size: 20px;
    background-color: #20b2aa;
}

button:nth-child(8) {
    font-size: 20px;
    background-color: #ffa500;
}

button:nth-child(12) {
    font-size: 20px;
    background-color: #f08080;
}

button:nth-child(16) {
    font-size: 20px;
    background-color: #7d93e0;
}

button:nth-child(20) {
    font-size: 20px;
    background-color: #9477af;
}

body {
    font-family: Roboto;
    background: #373B44;
    background: -webkit-linear-gradient(to right, #4286f4, #373B44);
    background: linear-gradient(to right, #4286f4, #373B44);
}

#may_tinh {
    width: 320px;
    height: 520px;
    background-color: #eaedef;
    top: 20px;
    margin: 0 auto;
    position: relative;
    border-radius: 5px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

#ket_qua {
    height: 120px;
}

#ket_qua_cu {
    text-align: right;
    height: 20px;
    margin: 0 20px;
    padding-top: 20px;
    font-size: 15px;
    color: #919191;
}

#xuat_ket_qua {
    text-align: right;
    height: 60px;
    margin: 10px 20px;
    font-size: 30px;
}

#ban_phim {
    height: 400px;
}
</style>
