<script lang="ts">
	import type { PageData } from "./$types";

	export let data: PageData;

	// instead of using
	// const { posts } = data
	// we use $: () for reactivity
	// we also use this whole thing i n the first place
	// so that we dont have to write data.posts.length
	// just posts.length
	$: ({ posts } = data);
</script>

<h1>Posts</h1>

<p>Showing {posts.length} posts.</p>

{#each posts as post}
	<ul>
		<li>
			<a href="/posts/{post.slug}">{post.title}</a>
		</li>
	</ul>
{/each}
