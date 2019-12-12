<template>
 <div> 

  <div class="plate" v-if="plateNumber === 1">
		<div class="cover-content-wrapper">
			<div class="cover-content">
				<img class="title-img" src="@/assets/pictures/html.png" alt="HTML">
				<div class="title">Test your site layout knowledge</div>
				<p>Answer a series of questions, get an assessment of knowledge, a list of lessons to pull up your level and training manual from our course “Profession: Front-end developer.”</p>
				<a href="#" class="button" @click.prevent=" plateNumber++ ">Take the test</a>
			</div>   
		</div>  
	</div>

  <!-- plate -->
	<div class="plate" v-if="plateNumber === 2">

		<!-- plate-header -->
		<div class="plate-header">
			<div class="plate-header__icon">
				<img src="@/assets/icons/list.png" alt="Icon">
			</div>
			<div class="plate-header__title">Your level of knowledge of layout sites</div>
		</div>
		<!-- // plate-header -->

		<!-- Content ... -->
		<div class="plate-content">
			<h2 class="title-main">What does HTML abbreviation mean?</h2>
			<div class="radio-group">

				<label
				v-for="item of plate1Variants"
				v-bind:key="item"
				v-bind:class="{
					'radio-block': true,
					'radio-block--active': item === plate1
				}" 
				@click="plate1 = item">
					<input type="radio" name="radio-group" class="radio-block__real" v-bind:checked=" item === plate1">
					<div class="radio-block__fake"></div>
					<div class="radio-block__text">{{ item }}</div>
				</label>
				
			</div>
		</div>

		<!-- plate-footer -->
		<div class="plate-footer">
			<div class="plate-footer__progress">

				<div class="progress">
					<div class="progress__label">
						Done: <strong>33%</strong>
					</div>
					<div class="progress__line-wrapper">
						<div class="progress__line-bar" style="width: 33%;"></div>
					</div>
				</div>

			</div>
			<div class="plate-footer__buttons">
				<a href="#" class="button button--back" @click.prevent=" plateNumber-- ">Back</a>
				<a href="#" class="button" @click.prevent="() => plate1 === null ? '' : plateNumber++ ">Further</a>
			</div>
		</div>
		<!-- // plate-footer -->

	</div>
	<!-- //plate -->

  <!-- plate -->
	<div class="plate" v-if="plateNumber === 3">

		<!-- plate-header -->
		<div class="plate-header">
			<div class="plate-header__icon">
				<img src="@/assets/icons/list.png" alt="Icon">
			</div>
			<div class="plate-header__title">Your level of knowledge of layout sites</div>
		</div>
		<!-- // plate-header -->

		<!-- Content ... -->
		<div class="plate-content">
			<h2 class="title-main">What does HTML abbreviation mean?</h2>
			<div class="checkbox-group">

				<label
				class="checkbox-block"
				v-for="item of plate2Variants"
				v-bind:key="item"
				v-bind:class="{'checkbox-block--active': plate2.includes(item)}"
				@click.prevent="toggleElement(plate2, item)"
				>
					<input type="checkbox" name="radio-group" class="checkbox-block__real" v-bind:checked="plate2.includes(item)">
					<div class="checkbox-block__fake"></div>
					<div class="checkbox-block__text">{{ item }}</div>
				</label>

				
			</div>
		</div>

		<!-- plate-footer -->
		<div class="plate-footer">
			<div class="plate-footer__progress">

				<div class="progress">
					<div class="progress__label">
						Done: <strong>66%</strong>
					</div>
					<div class="progress__line-wrapper">
						<div class="progress__line-bar" style="width: 66%;"></div>
					</div>
				</div>

			</div>
			<div class="plate-footer__buttons">
				<a href="#" class="button button--back" @click.prevent=" plateNumber-- ">Back</a>
				<a href="#" class="button" @click.prevent="() => plate2.length === 0?'': plateNumber++">Further</a>
			</div>
		</div>
		<!-- // plate-footer -->

	</div>
	<!-- //plate -->

  <!-- plate -->
	<div class="plate" v-if="plateNumber === 4">

		<!-- plate-header -->
		<div class="plate-header">
			<div class="plate-header__icon">
				<img src="@/assets/icons/list.png" alt="Icon">
			</div>
			<div class="plate-header__title">Your level of knowledge of layout sites</div>
		</div>
		<!-- // plate-header -->

		<!-- Content ... -->
		<div class="plate-content">
			<h2 class="title-main">In HTML you can create:</h2>

			<div class="cards-group">

				<label
				class="card-block"
				v-for="item of plate3Variants" 
				v-bind:key="item"
				@click="plate4 = id"
				>
					<div class="card-block__radio">
						<input name="image-group" type="radio" class="card-block__radio-real" v-bind:checked="plate4 === id">
						<div class="card-block__radio-fake"></div>
					</div>
					<div class="card-block__radio"></div>
					<div class="card-block__img">
						<img :src="item.img" alt="Img">
					</div>
					<div class="card-block__text">
						{{ item.title }}
					</div>
				</label>
				
			</div>


		</div>

		<!-- plate-footer -->
		<div class="plate-footer">
			<div class="plate-footer__progress">

				<div class="progress">
					<div class="progress__label">
						Done: <strong>100%</strong>
					</div>
					<div class="progress__line-wrapper">
						<div class="progress__line-bar" style="width: 100%;"></div>
					</div>
				</div>

			</div>
			<div class="plate-footer__buttons">
				<a href="#" class="button button--back" @click.prevent="plateNumber--">Back</a>
				<a href="#" class="button" @click.prevent="plate4 === null?'': plateNumber++">Further</a>
			</div>
		</div>
		<!-- // plate-footer -->

	</div>
	<!-- //plate -->

  <div class="plate" v-if="plateNumber === 5"> 
		<div class="cover-content-wrapper">
			<div class="cover-content">

				<img class="title-img" width="70" src="@/assets/icons/clapping.svg" alt="Fine! Last step!">
				<div class="title">Fine! Last step!</div>

				<div class="form-group">
					<label class="label" for="email">Enter Email:</label>
					<input class="input-email" type="email" id="email" placeholder="Your Email" v-model="email">
				</div>

				<input class="button button--huge" type="submit" value="Get Results" @click="agreement && email.trim().length && plateNumber++">

				<label class="checkbox">
					<input type="checkbox" class="checkbox__real" v-model="agreement">
					<div class="checkbox__fake"></div>
					<div class="checkbox__text">I have read the privacy policy</div>
				</label>

			</div>
		</div>
	</div>


  <div class="plate" v-if="plateNumber === 6">
		<div class="cover-content-wrapper">
			<div class="cover-content">

				<img class="title-img" width="70" src="@/assets/icons/clapping.svg" alt="Thanks!">
				<div class="title">Thanks!</div>
				<p>The results of your test and training manual have already been sent to you by Email.</p>
				<div class="title-2">Your bonuses:</div>
				<div class="bonus-cards-wrapper">
					<div class="bonus-card">
						<img class="bonus-card__img" src="@/assets/icons/leaflet.svg" alt="">
						<div class="bonus-card__title">Manual from the course on Front-end developer</div>
					</div>
					<div class="bonus-card">
						<img class="bonus-card__img" src="@/assets/icons/video-tutorial.png" alt="">
						<div class="bonus-card__title">Video lesson from the Front-end developer course</div>
					</div>
				</div>

			</div>
		</div>
	</div>

  </div> 

</template>

<script>


export default {
  

  data () {
    return {
		plateNumber: 1,
		plate1Variants:[ 
			"Hero Tutorial Multi Level", 
			"Hyper Text Markup Language", 
			"High Task Mirage Language", 
			"HTML has no decryption. This is a military development." ],
		plate2Variants:[
			"Hero Tutorial Multi Level", 
			"Hyper Text Markup Language", 
			"High Task Mirage Language", 
			"HTML has no decryption. This is a military development." ],
		plate3Variants:[
			{
				id: 0,
				title: "Mobile applications",
				img: "pictures/mobile.jpg"
				
			},
			{
				id: 1,
				title: "Sites for all browsers and platforms",
				img: "pictures/browser.jpg"
			},
			{
				id: 2,
				title: "Windows software",
				img: "pictures/windows.jpg"
			},
			{
				id: 3,
				title: "Linux software",
				img: "pictures/linux.jpg"	
			}
		],
		plate1: null,
		plate2:[],
		plate3: null,
		plate4: null,
		email:'',
		agreement: false  
	}
  },
  methods:{toggleElement (array, item) {
		if (array.includes(item)) {
			const index = array.indexOf(item);
			array.splice(index, 1)
		}
		else {
			array.push(item)
		}

		
		
	}
}
  
}
</script>

