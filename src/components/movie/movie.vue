<template  lang='html'>
	<transition appear name='slide-fade'>
		<section class='single-movie-wrapper'>
			<img v-if='selectedMovie.Poster != "N/A"'>
		</section>
	</transition>
</template>

<script></script>

<style lang='css'>
	.single-movie-wrapper {
		background: #fff;
		box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.2);
		color: #444;
		border-radius: 10px;
		display: grid;
		grid-gap: 1rem;
		grid-template-areas: "poster movie" "poster footer";
		grid-template-columns: min-content 1fr;
		grid-template-rows: min-content 1fr;	
	}

	.movie-poster {
		grid-area: poster;
	}

	.movie-data {
		grid-area: movie;
		padding: 0 1rem;
	}

	.movie-data > h2 {
		color: #666;
		padding-bottom: 1rem;
		border-bottom: 1px solid gainsboro;
	}


	.movie-data > .plot {
		font-size: .8rem;
	}
	.movie-data > .plot {
		font-size: .8rem;
	}
	dl {
		font-size: .8rem;
		margin:0;
	}
	dt {
		float: left;
		clear: left;
		width: 4rem;
		font-weight: bolder;
	}
	dd {
		margin: 0 0 0 4rem;
		padding: 0 0 0.5rem 0;
	}
	.movie-footer {
		grid-area: footer;
		padding: 0.1rem;
	}
	.slide-fade-enter-active {
		transition: all .4s ease;
	}
	.slide-fade-leave-active {
		transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
	}
	.slide-fade-enter, .slide-fade-leave-to {
		transform: translateY(-1rem);
		opacity: 0;
	}
	.slide-right-fade-enter--active {
		transition: all .8s ease;
	}
	.slide-right-fade-leave-active {
		transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
	}
	.slide-right-fade-enter, .slide-fade-leave-to {
		transform: translateX(2rem);
		opacity: : 0;
	}
</style>