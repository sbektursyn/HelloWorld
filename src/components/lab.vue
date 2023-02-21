<script>
	export default{
		data(){
			return{
				samiso: false,
				gestapo: 'работает'
			}
		}
	}
</script>

<template>
<body>
	<p>Hello World</p>
	<table>
		<tr>
			<td></td>
			<td>Code</td>
			<td>Name</td>
			<td>Fname</td>
			<td>Age</td>
			<td>Phone</td>
		</tr>
		<tr>
			<td v-if="samiso">></td>
			<td v-if="samiso">5</td>
			<td v-if="samiso">Маша</td>
			<td v-if="samiso">Машина</td>
			<td v-if="samiso">23</td>
			<td v-if="samiso">222222222</td>
		</tr>
		<tr>
			<td></td>
			<td v-if="samiso">6</td>
			<td v-if="samiso">Cаша</td>
			<td v-if="samiso">Сашина</td>
			<td v-if="samiso">24</td>
			<td v-if="samiso">333333333</td>
		</tr>
		<tr>
			<td></td>
			<td v-if="samiso">7</td>
			<td v-if="samiso">Даша</td>
			<td v-if="samiso">Дашина</td>
			<td v-if="samiso">19</td>
			<td v-if="samiso">444444444</td>
		</tr>
		<tr>
			<td v-if="samiso"></td>
			<td v-if="samiso">8</td>
			<td v-if="samiso">Вася</td>
			<td v-if="samiso">Сергеевич</td>
			<td v-if="samiso">22</td>
			<td v-if="samiso">5555555555</td>
		</tr>
		<tr>
			<td>*</td>
			<td></td>
			<td></td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
	</table>
	<p v-if="samiso" class="text">{{gestapo}}</p>
	
	<button class="btn" @click="samiso = !samiso;">button 1</button>
</body>
</template>

<style>
	.btn{
		/*position: absolute;
		width: 70px;
		height: 30px;
		margin-left: 140px;*/
	}
	.text{
		position: absolute;
		margin-top: 100px;
	}
</style>