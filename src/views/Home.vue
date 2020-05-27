<template>
	<div class="home">
		<AppHeader />
		<div class="details">
			<form>
				<div class="route-details">
					<label for="route-id">ROUTE ID:</label>
					<input type="text" name="route-id" id="route-id" placeholder="Route ID">
				</div>
				<div class="route-details">
					<label for="route-name">ROUTE NAME:</label>
					<input type="text" name="route-name" id="route-name" placeholder="Source-Destination">
				</div>
			</form>
			<StopList class="route-details" />
			<input type="button" id="submit" value="Add Route" disabled>
		</div>
	</div>
</template>

<script>
// @ is an alias to /src
import StopList from '@/components/StopList.vue'
import AppHeader from '@/components/Header.vue'

export default {
	name: 'Home',
	components: {
		StopList,
		AppHeader
	}
}
</script>

<style>
	*{
		font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
		font-weight: bold;
		color: #002C3E;
	}

	.details{
		position: absolute;
		margin: 10px;
		margin-top: 50px;
		left: 200px;
	}

	#route-id, #route-name{
		float: right;
		width: 400px;
		height: 25px;
		box-sizing: content-box;
		text-align: center;
		font-family: 'Courier New', Courier, monospace;
	}

	.route-details{
		padding: 20px;
		margin: 20px;
	}

	#submit{
		float: right;
		margin-right: 40px;
		background-color: #002C3E;
		border-width: 2px;
		border-color: #002C3E;
		color: white;
		padding: 15px;
		font-size: 20px;
		border-radius: 10px;
		cursor: pointer;
	}

	#submit:hover{
		background: none;
		color: #002C3E;
		transition: 0.2s;
	}

	#submit:disabled, #submit:disabled:hover {
		background-color: #002C3E;
		color: grey;
		cursor: not-allowed;
	}

</style>