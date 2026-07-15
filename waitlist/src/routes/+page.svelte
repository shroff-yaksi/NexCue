<script lang="ts">
	// Throwaway waitlist landing — UI + client state only.
	// NO backend: submitting does not send the email anywhere yet.
	// Wiring Resend (email capture) is a separate, human-gated follow-on.

	let email = $state('');
	let submitted = $state(false);
	let error = $state('');

	// Minimal, forgiving email shape check — good enough for a landing page.
	const EMAIL_RE = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

	function handleSubmit(event: SubmitEvent) {
		event.preventDefault();
		const value = email.trim();
		if (!EMAIL_RE.test(value)) {
			error = 'Please enter a valid email address.';
			return;
		}
		error = '';
		// TODO(follow-on): POST to the Resend-backed endpoint. For now, local state only.
		submitted = true;
	}
</script>

<svelte:head>
	<title>NexCue — decide what to do next</title>
	<meta
		name="description"
		content="One inbox for everything you save, and one Decide flow that picks the single right thing by your time and mood. Join the waitlist."
	/>
</svelte:head>

<main class="flex min-h-screen flex-col items-center justify-center px-6 py-16">
	<section class="w-full max-w-xl text-center">
		<p
			class="mb-6 inline-block rounded-full border border-brand/20 bg-brand/5 px-3 py-1 text-sm font-medium text-brand"
		>
			Early access
		</p>

		<h1 class="text-4xl font-semibold tracking-tight text-ink sm:text-5xl dark:text-white">
			Stop scrolling. <span class="text-brand">Start</span> what you saved.
		</h1>

		<p class="mx-auto mt-5 max-w-lg text-lg leading-relaxed text-ink-soft">
			NexCue is one inbox for everything you save — and a <strong
				class="font-semibold text-ink dark:text-white">Decide</strong
			>
			flow that picks the single right thing by your time and mood. One tap to start.
		</p>

		{#if submitted}
			<div
				class="mx-auto mt-10 max-w-md rounded-[var(--radius-card)] border border-success/30 bg-success/5 p-6"
				role="status"
				aria-live="polite"
			>
				<p class="text-lg font-semibold text-success">You're on the list.</p>
				<p class="mt-1 text-sm text-ink-soft">
					We'll email <span class="font-medium text-ink dark:text-white">{email.trim()}</span> when NexCue
					opens up.
				</p>
			</div>
		{:else}
			<form
				class="mx-auto mt-10 flex w-full max-w-md flex-col gap-3 sm:flex-row"
				novalidate
				onsubmit={handleSubmit}
			>
				<div class="flex-1 text-left">
					<label for="email" class="sr-only">Email address</label>
					<input
						id="email"
						name="email"
						type="email"
						autocomplete="email"
						placeholder="you@example.com"
						bind:value={email}
						oninput={() => (error = '')}
						aria-invalid={error ? 'true' : undefined}
						aria-describedby={error ? 'email-error' : undefined}
						class="w-full rounded-[var(--radius-card)] border border-ink-soft/25 bg-surface px-4 py-3 text-base text-ink outline-none transition focus:border-brand focus:ring-2 focus:ring-brand/30 dark:bg-slate-800 dark:text-white"
					/>
				</div>
				<button
					type="submit"
					class="rounded-[var(--radius-card)] bg-brand px-6 py-3 text-base font-semibold text-white transition hover:bg-brand-600 focus:ring-2 focus:ring-brand/40 focus:outline-none"
				>
					Join the waitlist
				</button>
			</form>

			{#if error}
				<p id="email-error" class="mt-2 text-sm text-error" role="alert">{error}</p>
			{/if}

			<p class="mt-4 text-sm text-ink-soft">No spam. One email when it's ready.</p>
		{/if}
	</section>
</main>
