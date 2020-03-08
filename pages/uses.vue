<template>
	<main class="uses">
		<header>
			Following the latest trend where people share their day-to-day setups and gear, here's my
			<a href="https://uses.tech/">/uses</a> listing.
			<br><br>
			I'm personally not huge into any ecosystem in general.
			I tend to go for anything that fits my usecase at the time and also have multiple setups I swap between.
		</header>
		<h2 id="software">Software</h2>
		<div class="responsive-row">
			<Box>
				<ul>
					<h3>Editor</h3>
					<Li main="VS Code" desc="Looking for lightweight alternatives but pretty much stuck with VSCode."/>
					<Li main="Fira Code font with ligatures" desc="Can't live without this font anymore. I use it everywhere I can."/>
					<Li main="Darker+ theme" desc="I'm working on a color theme based on darker+ but it's still long way to go."/>
				</ul>
			</Box>
			<Box :image="true">
				<ImageThumb
					title="Some code on a dirty screen."
					src="code.jpg"
					thumbSrc="code.jpg"
					alt="code.jpg"
				/>
			</Box>
		</div>
		<h2 id="hardware">Hardware</h2>
		<Box>
			<ul>
				<h3>Home PC</h3>
				<Li main="System build from scratch" desc="Overclocked 4690k, 1660ti, 16gb ram, etc... Nothing fancy but get's the job done."/>
				<Li main="Linux Ubuntu / Windows 10 dual boot setup" desc="Windows for gaming, Ubuntu for productivity."/>
				<Li main="AOC 144hz 1080p main monitor"/>
				<Li main="Samsung 1080p secondary vertical monitor"/>
				<Li main="Razer deathadder chroma"/>
				<Li main="Ikea lift table, ikea chair..." desc="Yes, I'm a sucker for that cheap Ikea goodness."/>
			</ul>
		</Box>
		<Box>
			<ul>
				<h3>Laptop</h3>
				<Li main="Lenovo ThinkPad x230" desc="Bought secondhand from some corporation."/>
				<Li main="Upgraded to 16gb ram"/>
				<Li main="256gb aftermarket ssd"/>
				<Li main="Aftermarket large battery"/>
				<Li main="Linux mint"/>
			</ul>
		</Box>
		<Box>
			<ul>
				<h3>Misc</h3>
				<Li main="Ducky x Varmilo MIYA-Pro Panda 65% keyboard" desc="This thing goes everywhere with me. I carry it to work and back everyday."/>
				<Li main="Sony WH-1000XM3 noise cancelling headphones"/>
			</ul>
		</Box>
	</main>
</template>

<script>
import ImageThumb from "~/components/ImageThumb.vue";
import Li from "~/components/Li.vue";
import Box from "~/components/Box.vue";

export default {
	head() {
		return {
			title: "Teemu Karppinen /uses"
		};
	},
	components: {
		ImageThumb,
		Box,
		Li,
	},
};
</script>

<style lang="scss">
@import "@/layouts/theme.scss";

.uses header {
	padding: 10rem 0;
	font-size: 1.5rem;
}

ul {
	h3 {
		margin-bottom: 1rem;
	}
}

</style>
