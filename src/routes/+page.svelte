<script>
	// @ts-nocheck
	import { Slide } from '$lib/components';
	import { Fa } from 'svelte-fa';
	import {
		faChalkboardTeacher,
		faNewspaper,
		faThumbsUp,
		faCalendarAlt
	} from '@fortawesome/free-solid-svg-icons';
</script>

{#snippet heading(icon, text)}
	<h2>
		<Fa {icon} />
		<span>{@html text}</span>
	</h2>
{/snippet}

<Slide id="about-us">
	<div class="content content-right">
		{@render heading(faChalkboardTeacher, 'Tailored Python Training Just for <strong>You</strong>')}
		<article>
			<p>
				Our personalized, long-term Python training is designed to fit your unique goals and
				schedule.<br />Whether you're a beginner or a professional, we'll help you build the skills
				you need to succeed.
			</p>
			<p>Join us and take control of your learning journey!</p>
		</article>
		<a href="#get-started" class="cta">Start Learning</a>
	</div>
</Slide>

<Slide id="blog">
	<div class="content content-left">
		<article>
			{@render heading(faNewspaper, 'Stay Updated')}
			<p>
				Get the latest insights, tutorials, and news in Python development. Keep up with industry
				trends and never stop learning.
			</p>
			<a href="/blog" class="cta">Visit Our Blog</a>
		</article>
	</div>
</Slide>

<Slide id="recommendations">
	<div class="content content-right">
		{@render heading(faThumbsUp, 'Recommendations')}
		<article>
			<p>
				Lorem, ipsum dolor sit amet consectetur adipisicing elit. Blanditiis fugit eos doloremque
				explicabo molestiae inventore voluptatibus provident eius eveniet! Sint eligendi quo rerum
				fuga laborum nam atque perferendis porro nesciunt!
			</p>
			<p>
				Quis eveniet temporibus maiores corrupti magnam expedita quae, ea consequuntur numquam
				quidem! Lorem ipsum dolor sit amet consectetur, adipisicing elit. Dolorem.
			</p>
		</article>
		<a href="/trainers" class="cta">Meet the Trainers</a>
	</div>
</Slide>

<Slide id="get-started">
	<div class="content content-center">
		{@render heading(faCalendarAlt, 'Book a Free Session')}
		<article>
			<p>
				Meet your trainer, discuss your goals, and start your customized learning plan today with a
				free, no-obligation session.
			</p>
		</article>
		<a href="/signup" class="cta">Get Started Now</a>
	</div>
</Slide>

<style>
	.content {
		display: flex;
		flex-direction: column;
		justify-content: center;
		gap: 1rem;
		height: 100%;
	}

	.content-right {
		align-items: flex-end;
		text-align: right;
	}

	.content-left {
		align-items: flex-start;
		text-align: left;
	}

	.content-center {
		align-items: center;
		text-align: center;
	}

	:global(#about-us) {
		background: linear-gradient(135deg, #1e3799, #4a69bd);
		color: var(--layout-color);
	}

	:global(#blog) {
		background: white;
		color: black;
	}

	:global(#recommendations) {
		background: linear-gradient(135deg, #306998, #00796b);
		color: var(--layout-color);
	}

	:global(#get-started) {
		background: white;
		color: black;
	}

	h2 {
		font-size: 3rem;
		margin-bottom: 1rem;
		display: inline-flex;
		align-items: center;
		justify-content: center;
		flex-wrap: wrap;
		gap: 1rem;
	}

	article p {
		font-size: 1.5rem;
		margin-bottom: 2rem;
	}
	.cta {
		font-size: 1.3rem; /* Increase the font size for the buttons */
		background: linear-gradient(135deg, var(--layout-background-color), #4a69bd);
		color: var(--layout-color);
		padding: 1rem 1.5rem;
		border-radius: 5px;
		text-decoration: none;
		font-weight: bold;
		transition: transform 0.3s ease;
		align-self: flex-start;
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
	}

	.cta:hover {
		background: linear-gradient(135deg, #4a69bd, var(--layout-background-color));
		transform: scale(1.05);
		box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
	}

	:global(#about-us) .cta,
	:global(#recommendations) .cta {
		align-self: flex-end;
	}

	:global(#get-started) .cta {
		align-self: center;
	}
</style>
