<script>
	export default {
		components: {
			props: ['doctor','patient','date','time','complaints'],
			emits: ['remove']
		},
		data(){
			return {
				newAppDoctor: '',
				newAppPatient: '',
				newAppDate: '',
				newAppTime: '',
				newAppComplaints: '',
				newAppDoctor2: '',
				newAppPatient2: '',
				newAppDate2: '',
				newAppTime2: '',
				newAppComplaints2: '',
				appId: '',
				apps: [
					{
						id:1,
						Doctor: 'Mr. Brown',
						Patient: 'Mr. Wesley',
						Date: '2010-12-23',
						Time: '13:00',
						Complaints: 'stomack ache'
					}
				],
				nextAppId: 2
			}
		},
		methods: {
			addNewApp() {
				this.apps.push({
					id: this.nextAppId++,
					Doctor: this.newAppDoctor,
					Patient: this.newAppPatient,
					Date: this.newAppDate,
					Time: this.newAppTime,
					Complaints: this.newAppComplaints
				})
				this.newAppDoctor = ''
				this.newAppPatient = ''
				this.newAppDate = ''
				this.newAppTime = ''
				this.newAppComplaints = ''
			},
			copyNewApp(app) {
				this.newAppDoctor2 = app.Doctor,
				this.newAppPatient2 = app.Patient,
				this.newAppDate2 = app.Date,
				this.newAppTime2 = app.Time,
				this.newAppComplaints2= app.Complaints,
				this.appId = app
			},
			editNewApp(app) {
				this.appId.Doctor = this.newAppDoctor2,
				this.appId.Patient = this.newAppPatient2,
				this.appId.Date = this.newAppDate2,
				this.appId.Time = this.newAppTime2,
				this.appId.Complaints = this.newAppComplaints2
			}
		}
	}
</script>


<template>
<body>
	<form v-on:submit.prevent="addNewApp" class="appointment">
		<label for="doctor" class="forms">Doctor:</label><input v-model="newAppDoctor" id="doctor" class="forms">

		<label for="patient" class="forms">Patient:</label><input v-model="newAppPatient" id="patient" class="forms">

		<label for="date" class="forms">Date:</label><input v-model="newAppDate" id="date" class="forms" type="date">  

		<label for="time" class="forms">Time:</label><input v-model="newAppTime" id="time" class="forms" type="time">

		<label for="complaints" class="forms">Complaints:</label><input type="text" v-model="newAppComplaints" id="complaints" class="forms">

		<button class="add">Add</button>
	</form>
	<div>
		<table >
			<tr>
				<td>
					ID
				</td>
				<td>
					Doctor
				</td>
				<td>
					Patient
				</td>
				<td>
					Date
				</td>
				<td>
					Time
				</td>
				<td>
					Complaints
				</td>
			</tr>
			<tr v-for="(app, index) in apps" :key="app.id">
				<td>
					{{app.id}}
				</td>
				<td>
					{{app.Doctor}}
				</td>
				<td>
					{{app.Patient}}
				</td>
				<td>
					{{app.Date}}
				</td>
				<td>
					{{app.Time}}
				</td>
				<td>
					{{app.Complaints}}
				</td>
				<td>
					<button @click="apps.splice(index, 1)" class="btn">delete</button>
					<button @click="copyNewApp(app)" class="btn">edit</button>
				</td>
			</tr>
		</table>
	</div>
	<form v-on:submit.prevent="editNewApp" class="appointment2">
		<label for="doctor2" class="forms">Doctor:</label><input v-model="newAppDoctor2" id="doctor2" class="forms">

		<label for="patient2" class="forms">Patient:</label><input v-model="newAppPatient2" id="patient2" class="forms">

		<label for="date2" class="forms">Date:</label><input v-model="newAppDate2" id="date2" class="forms" type="date">  

		<label for="time2" class="forms">Time:</label><input v-model="newAppTime2" id="time2" class="forms" type="time">

		<label for="complaints2" class="forms">Complaints:</label><input type="text" v-model="newAppComplaints2" id="complaints2" class="forms">

		<button class="add" @click="editNewApp(app)">edit</button>
	</form>
</body>
</template>

<style>
	body{
		display: flex;
	}
	form {
		display: flex;
		flex-direction: column;
	}
	table,td{
		border:1px solid black;
	}
	td{
		min-width: 80px;
		max-width: 100px;
		overflow-x: scroll;
	}
	table{
		position: absolute;
		margin-top: -230px;
		margin-left: -280px;
		text-align: center;
		font-size: 13px;
	}
	.appointment{
		position: absolute;
		margin-left: -650px;
		border: 2px solid black;
		width: 300px;
		border-radius: 10px;
	}
	.appointment2{
		position: absolute;
		margin-left: 370px;
		border: 2px solid darkblue;
		width: 300px;
		border-radius: 10px;
	}
	.forms{
		margin:10px;
		margin-bottom: 0;
	}
	input{
		border:1px solid black;
		border-radius: 10px;
		height: 30px;
	}
	.add{
		width: 100px;
		height: 30px;
		margin: 20px auto;
		border: 1px solid black;
		border-radius: 10px;
	}
	.add:hover{
		border-color: #888;
	}
	.add:active{
		background: #888;
	}
	#complaints{
		height: 50px;
	}
	#complaints2{
		height: 50px;
	}
	.btn{
		width: 50px;
		border:1px solid black;
		border-radius: 5px;
	}
	.btn:hover{
		border-color: #888;
	}
	.btn:active{
		background: #888;
	}
</style>




















