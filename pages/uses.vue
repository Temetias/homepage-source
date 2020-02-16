<template>
	<main>
		<header>
			Following the latest trend where people share their day-to-day setups and gear, here's my
			<a href="https://uses.tech/">/uses</a> listing. I'm personally not huge into any ecosystem in general.
			I tend to go for anything that fits my usecase at the time and also have multiple setups I swap between. 
		</header>
		<h2>Software</h2>
		<p>
			<ul>
				<h3>Editor</h3>
				<Li main="VS Code" desc="Looking for lightweight alternatives but pretty much stuck with VSCode."/>
				<Li main="Fira Code font with ligatures" desc="Can't live without this font anymore. I use it everywhere I can."/>
				<Li main="Darker+ -theme" desc="I'm working on a color theme based on darker+ but it's still long way to go."/>
			</ul>
		</p>
		<h2>Personal hardware</h2>
		<p>
			<ul>
				<h3>Home PC</h3>
				<Li main="System build from scratch" desc="Overclocked 4690k, 1660ti, 16gb ram, etc... Nothing fancy but get's the job done."/>
				<Li main="Linux Ubuntu / Windows 10 dual boot setup" desc="Windows for gaming, Ubuntu for productivity."/>
				<Li main="AOC 144hz 1080p main monitor"/>
				<Li main="Samsung 1080p secondary vertical monitor"/>
				<Li main="Razer deathadder chroma"/>
				<Li main="Ikea lift table, ikea chair..." desc="Yes, I'm a sucker for Ikea stuff."/>
			</ul>
		</p>
		<p>
			<ul>
				<h3>Laptop</h3>
				<Li main="Lenovo ThinkPad x230" desc="Bought secondhand from some corporation."/>
				<Li main="Upgraded to 16gb ram"/>
				<Li main="256gb aftermarket ssd"/>
				<Li main="Aftermarket large battery"/>
				<Li main="Linux mint"/>
			</ul>
		</p>
		<p>
			<ul>
				<h3>Misc</h3>
				<Li main="Ducky x Varmilo MIYA-Pro Panda TKL keyboard" desc="This thing goes everywhere with me. I carry it to work and back everyday."/>
				<Li main="Sony WH-1000XM3 noise cancelling headphones"/>
			</ul>
		</p>
		<h2>Work hardware</h2>
		<p>
			<ul>
				<h3>Setup</h3>
				<Li main="Dell xps 13" desc="Docks to rest of the setup via a thunderbolt 3 dock."/>
				<Li main="Windows 10" desc="Would go Linux but currently need Windows for some projects."/>
				<Li main="OnePlus 7T PRO"/>
				<Li main="Logitech MX master, 1080p dell monitor, lift table, etc..." desc="All and all a nice comfy setup to work with. Thanks PG! :)"/>
			</ul>
		</p>
		<ImageThumb class="image"
			:openable="true"
			title="My computer."
			src="/test-image.jpg"
			alt="test-image.jpg"
		/>
	</main>
</template>

<script>
import ImageThumb from "~/components/ImageThumb.vue";
import Li from "~/components/Li.vue";

export default {
	components: {
		ImageThumb,
		Li,
	},
};
</script>

<style lang="scss">
@import "@/layouts/theme.scss";

ul {
	h3 {
		margin-bottom: 1rem;
	}
}

</style>