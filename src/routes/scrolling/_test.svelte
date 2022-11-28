<script lang="ts">
	import './test.css';
	let scrollPosition: number = 1;
	let container: HTMLElement;
	let previous = '';
	let offset = 0;
	let linePosition = 0;

	let textLines: [];
	$: if (container) {
		// console.log('CONTAINER\n', container);
		let paragraph = document.getElementById('textContent');
		let content = paragraph.innerHTML.replace(/  |^\s+|\s+$/g, '');
		textLines = content.split(/(?<=[.!?])/g);

		// let html = document.getElementById('textContent')?.innerHTML;
		// for (let i in textLines) {
		// 	html += `<span id='id_'${i}>${textLines[i]}</span>`;
		// }
	}

	function scrolling() {
		// for (let i in textLines) {
		// 	let current = document.querySelector('#id_' + i + '');
		// 	if (current) {
		// 		let currentTop = current.offSetTop;
		// 		if (scrollPosition <= 0) {
		// 			document.querySelector('#id_0')?.className += ' strikeThrough';
		// 		}
		// 		if (scrollPosition >= currentTop - 50) {
		// 			if (!current?.hasClass('strikeThrough')) {
		// 				current.addClass('strikeThrough');
		// 				if (previous) {
		// 					if (current.offsetTop == previous.offsetTop) {
		// 						previous.addClass('strikeThrough');
		// 					}
		// 				}
		// 			}
		// 		}
		// 	}
		// }
		if (typeof window !== 'undefined' && typeof document !== 'undefined' && textLines) {
			let container = document.getElementById('displayText');
			// console.log('LINE COUNT -> ', textLines.length);
			// console.log('CONTAINER CLIENT HEIGHT -> ', container?.clientHeight);
			// console.log('CONTAINER OFFSET HEIGHT -> ', container?.offsetTop);
			// console.log('SCROLL MAX -> ', container.scrollMaxY);
			let scrollCalc = container?.scrollHeight / textLines.length;
			linePosition = Math.ceil(scrollPosition / 8.15);
			// console.log(
			// 	'SCROLL HEIGHT -> ',
			// 	container?.scrollHeight,
			// 	scrollCalc,
			// 	scrollPosition,
			// 	linePosition
			// );
		}
	}

	$: if (scrollPosition >= 0) {
		// console.log('SCROLL POSITION -> ', scrollPosition);
		// console.log('LINES\n', textLines);
		// console.log('HTML\n', document.getElementById('textContent')?.innerHTML);
		scrolling();
	}
</script>

<div class="">
	<div class={'blogContainer '} style={'display: none'} id="textContainer" bind:this={container}>
		<!-- on:scroll={() => (scrollPosition = container.scrollTop)} -->
		<h1>Line Through Text Test</h1>
		<p class={`paragraphText`} id="textContent">
			<!-- Lorem ipsum dolor, sit amet consectetur adipisicing elit. Magni quia quis vero modi illum
			consectetur, quo dolorum, libero soluta similique nisi adipisci. Commodi minus, corrupti
			exercitationem libero impedit fuga unde rerum optio voluptatum, suscipit aperiam cupiditate?
			Enim numquam, quo itaque magni error sequi nisi debitis explicabo ab natus fuga blanditiis
			animi iste libero eius at delectus vitae nulla illum qui ex nihil aut, dolore facilis. Iure
			iusto voluptatem rem exercitationem animi sit, laboriosam dolores officiis quae perspiciatis
			sequi minima nostrum unde sunt, eligendi eius nobis omnis deleniti esse quam accusantium.
			Earum, ex necessitatibus ab incidunt quidem, perferendis ducimus tenetur accusantium mollitia
			esse sit, saepe quod ipsum explicabo corrupti voluptatem! Nulla deleniti repellendus id odit
			deserunt minus recusandae laudantium, fugiat officiis. Eius dicta optio eaque. Voluptatem
			minima quibusdam, corrupti, quaerat ad saepe fugit sunt, quod optio iste voluptate eos
			accusantium doloribus nobis asperiores ipsa! Consequatur corrupti facilis consectetur et ab,
			veniam neque amet non ut tempora animi, obcaecati dolore voluptates cum recusandae ex id ipsa
			ea deleniti. Adipisci eaque ab, repudiandae voluptate incidunt optio nisi qui. Velit
			cupiditate, quis magni repellendus excepturi voluptates neque enim voluptas molestiae
			repudiandae eos quas pariatur ipsum facilis sequi a, perferendis accusamus ab quia? Ducimus
			deleniti quas reiciendis ut earum eius sit similique ad alias rem, dolorem, dicta officia
			eaque asperiores saepe optio doloribus adipisci quaerat illum odit vel nihil impedit! Aliquam
			explicabo itaque earum provident cumque quae. Ut consectetur beatae ducimus! Iusto debitis
			atque saepe ipsum iure tempore quam ab soluta vero! Accusantium, iure possimus? -->
			Morty: (rubs his eyes) What, Rick? What’s going on? Rick: I got a surprise for you, Morty. Morty:
			It's the middle of the night. What are you talking about? Rick: (spills alcohol on Morty's bed)
			Come on, I got a surprise for you. (drags Morty by the ankle) Come on, hurry up. (pulls Morty out
			of his bed and into the hall) Morty: Ow! Ow! You're tugging me too hard! Rick: We gotta go, gotta
			get outta here, come on. Got a surprise for you Morty. [The scene cuts to Rick's ship] Rick: (Rick
			drives through the night sky) What do you think of this... flying vehicle, Morty? I built it outta
			stuff I found in the garage. Morty: Yeah, Rick... I-it's great. Is this the surprise? Rick: Morty.
			I had to... I had to do it. I had— I had to— I had to make a bomb, Morty. I had to create a bomb.
			Morty: What?! A bomb?! Rick: We're gonna drop it down there just get a whole fresh start, Morty.
			Create a whole fresh start. Morty: T-t-that's absolutely crazy! Rick: Come on, Morty. Just take
			it easy, Morty. It's gonna be good. Right now, we're gonna go pick up your little friend Jessica.
			Morty: Jessica? From my math class? Rick: (puts an arm around Morty’s shoulders) When I drop the
			bomb you know, I want you to have somebody, you know? I want you to have the thing. I'm gonna make
			it like a new Adam and Eve, and you're gonna be Adam. Morty: Ohh... Rick: And Jessica's gonna be
			Eve. Morty: Whhhh-wha? Rick: And so that's the surprise, Morty. Morty: No, you can't! (shoves Rick
			away) Jessica doesn't even know I exist! But—but, but forget about that, because you can't blow
			up humanity! Rick: I-I get what you're trying to say, Morty. Listen, I'm not... (spills alcohol
			down his shirt) You don't got... Y-you don’t gotta worry about me trying to fool around with Jessica
			or mess around with Jessica or anything. I'm not that kind of guy, Morty. Morty: What are you talking
			about, Rick? Rick: You-you don't have to worry about me getting with Jessica or anything. Sh-sh-she—
			she, she, she's all for you, Morty. Morty: I don't care about Jessica! Y-Yyyyyyyyyyou— Rick: You
			know what, Morty? You're right. (throws empty bottle into the backseat) Let's forget the girl altogether.
			She, she's probably nothing but trouble, anyways. (presses a button) Robot Voice: Arming neutrino
			bomb. Morty: (unbuckles his seatbelt) That's it... that's it, Rick. I'm taking the wheel. (jumps
			up on Rick and starts fighting with him over control of the wheel) Rick: Get off of me, Morty!
			(they begin to talk over each other) Morty: I'm taking charge of this situation, buddy! (starts
			kicking Rick's face while grabbing the wheel) I'm put—I’m, I'm, I'm, I'm puttin’... I-I’m, I’m,
			I’m not gonna stand around like some sort of dumb... dumb person and just le-let you ruin the whole
			world! Rick: (at the same time) Come on! What’s gotten into you? If you love Earth so much why
			don’t you marry it? (pushes Morty) What are you, crazy? Alright, alright, Morty. (pushes Morty
			off of him) Rick: Alright. I'll-I'll land. I'll land. I'll land. I'll land the thing. I’ll land
			the thing. Big tough guy all of a sudden. [Cut to desert] Rick: (Rick lands the cruiser in an open
			desert; he opens the door and tumbles out among dozens of empty alcohol cans and bottles) We'll
			park it right here, Morty. Right here on the side of the ree... road here. Morty: Oh, thank god.
			Rick: You know what? That was all a test, Morty. Just an elaborate test to make you more assertive.
			Morty: It was? Rick: Sure. Why not? I don’t, I don't know. Y-you know what, Mo— (falls asleep and
			begins snoring) Robot Voice: Neutrino bomb armed. Morty: Um... [Cut to opening theme] [Open to
			Smith residence, dining room] Jerry: I see there's a new episode of that singing show tonight.
			Who do you guys think is gonna be the best singer? (Morty falls asleep at the table, smashing his
			face into his plate) Summer: Oh my God, his head is in his food. I'm going to puke. Beth: Morty,
			are you getting sick? (Morty lifts his head, clearly exhausted, and wipes food from his face) I
			told you not to practice-kiss the living room pillow. The dog sleeps on it.
		</p>
	</div>

	<div
		class={'blogContainer '}
		id=""
		bind:this={container}
		on:scroll={() => (scrollPosition = container.scrollTop)}
	>
		<h1>Line Through Text Test</h1>
		<p class={`paragraphText`} id="displayText">
			{#each textLines || [] as line, index}
				<span style={`text-decoration: ${index < linePosition ? 'line-through' : ''}`}>{line}</span>
			{/each}
		</p>
	</div>
</div>
