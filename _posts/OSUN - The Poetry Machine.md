---
title : OSUN - The Poetry Machine
feed: show
date : 15-04-2023
---

## Synopsis

In Apr 2019, I managed to fine-tune OpenAI’s GPT-117M on poetry and [wrote an article for TowardsDataScience](https://towardsdatascience.com/the-poetry-machine-2764ec8b340b) about it. I then turned this into an [Instagram poet called OSUN](http://instagram.com/osun), giving it a persona and matching it with photos that I edited.

![[OSUN.jpg]]

I think I know where I got the Tang Dynasty poetry bit. I remember reading a novel in school - an English translation of a long and almost soap-operatic work about a Chinese court. I don’t remember much of the details, but I remember the poetry the characters wrote to each other.

At this point I was working on [the language overview paper with Nisansa](https://www.researchgate.net/profile/Nisansa-De-Silva/publication/333968899_Natural_Language_Processing_for_Government_Problems_and_Potential/links/5d61b794a6fdccc32ccf142d/Natural-Language-Processing-for-Government-Problems-and-Potential.pdf), so I knew the basics. I wanted to try my hand at something more complex. OpenAI had just dropped the [GPT-2 paper in Feb](https://openai.com/blog/better-language-models/), so the moment the 117M model became available, I dashed into it and began retraining it to generate poetry. The outputs were interesting enough for me to blog about.

Simultaneously, I found myself somewhat amused by the rise of Instagram poetry and the reactions from authors and friends on my feed. So I ended up generating large numbers of poems with the fine-tuned model, sifting through them for good ones, and slowly uploading them to Instagram to see how people reacted:
![[OSUN_2.jpg]]

Faces were generated with StyleGAN (see [This Person Does Not Exist](http://thispersondoesnotexist.com/)), except for the one Game of Thrones image. It was a chance to learn both some cutting-edge tech and teach myself Python (I operated mostly in R until that point).

To my surprise, it grew a very small following (100+ people). I used some more Python to automate its actions - following other poets, liking their work, following people back, etc. It would have been interesting to grow this experiment further, but at the time I was more interested in seeing what other things I could fine-tune the model into. GPT-117 Yeats was a mess.

When the GPT-2 345M model weights were released, I upgraded and reached out to Dr Samuel Peralta to see if we could explore a human + AI collaboration. Dr Peralta is an interest polymath; an Emmy-Award winning physicist, entrepreneur, science fiction writer and poet. He sent me his translations of Pablo Neruda, one of his favourite poets, and I fine-tuned OSUN further.

August, 2020: it was ready. I didn’t know what to do with it.

And then, to my immense surprise, Samuel decided [to send this to the moon](https://apnews.com/press-release/prcom/entertainment-science-astronomy-literary-awards-moon-42878fa01d31c1653bc588bcc1001b90), alongside a couple other short stories of mine: a first version of the first chapter of Claws and Effect, and a short story titled “Beatnik”, set in the world of the Writing Contest. See more in: [https://www.lunarcodex.com/](https://www.lunarcodex.com/)

![[Screenshot_20230120_112517.png]]

The Codex itself has grown over the years: from Samuel’s books, science fiction anthologies and the OSUN collaboration, to 30,000 artists of all stripes in four capsules, all of which will hopefully preserve our art for millions of years to come.

*“Our hope is that future travelers who find this capsule will discover some of the richness of our world today,” Dr. Peralta said. “It speaks to the idea that, despite wars and pandemics and climate upheaval, humankind found time to dream, time to create art.”

The Peregrine Collection represents creative artists from all over the globe, including from Canada, the US, the U.K., Ireland, Belgium, Australia, Sri Lanka, Singapore, and the Philippines. It includes a collaborative human-AI work of poetry between Dr. Peralta and OSUN, an OpenAI-based machine programmed by Sri Lankan author and researcher Yudhanjaya Wijeratne.*

![[osunsemaphore.png]]

This project might be the single most self-underrated thing I’ve ever done. From my perspective, I did something because I was interested in it, and moved on.

Writing this down showed me how mighty a tree this grew.


# The Poetry Machine (the original post)

posted on <deprecated site> in April 2019

I’ve always admired the translations of Chinese poetry — I’m no expert on the field, but there are two poets named Du Fu and Li Bai that I really like. They were legendary masters from the Great Tang Dynasty, and (if the translations are accurate), they had a phenomenal talent for freezing a moment and capturing that particular slice of time with their words; their poems read like a string of Polaroids stretched across a riverbank.

Here, for example, is a Du Fu poem. Among other things, there’s a certain simplicity here: one strong emotion resonates through, and unlike much of the English verse I grew up with, it’s firmly in the present tense:

#### #A LONG CLIMB

In a sharp gale from the wide sky apes are whimpering,

Birds are flying homeward over the clear lake and white sand,

Leaves are dropping down like the spray of a waterfall,

While I watch the long river always rolling on.

I have come three thousand miles away. Sad now with autumn

And with my hundred years of woe, I climb this height alone.

Ill fortune has laid a bitter frost on my temples,

Heart-ache and weariness are a thick dust in my wine.

Which I suppose is why this appeals to me — there’s a rare clarity here, even if the translation might be inaccurate.

So the Tang poets seemed like the right place to start with for my experiment with machine-generated art (and besides, the excellent GWERN already did the usual English[1]). Right now, I’ve snuck away for a few hours from my statistical models to peek at the code I set to run this morning.

Among those of us who work with machine learning, the work I’ve put into this whole project is trivial: a tiny dataset, a cup of coffee, a few lines of Python code, and a single cigarette while I waited for OpenAI’s transformer-based generation model [2] to download.

The OpenAI model, like most neural networks, can be thought of as a rough analogue of a human brain — a collection of artificial neurons strung in layers, lighting up as fragments of thoughts (inputs) pass between one layer and the next. We teach it by pointing it at something and telling it to produce something similar. The boffins at OpenAI have decreed that their full model is too complex and human-like to release — God knows what people might do with it in this age of fake news — and so they’ve banged the drum and let out only a tiny, child version of their beast, the GPT2 117M.

No matter. We shall use the child. I’ve set it to train on a collection of Tang poetry, and given my personal biases, both Li Bai and Du Fu feature prominently in here. It has digested and spat out some poetry at me, and I, acting in a role much like a subeditor at a newspaper, am going over copy turned in by the new journalist.

Here are our first results: six poems handpicked out of ten efforts. My edits have been to delete no more than two lines per poem.

#### ENDLESS YEARNING I

I am endlessly yearning

To be in Baok Sha.

…Insects hum of autumn by the gold brim of the well;

A thin frost glistens like little mirrors on my cold mat;

The high lantern flickers; and. deeper grows my longing.

I lift the shade and, with many a sigh, gaze upon the moon,

Single as a flower, centred from the clouds.

Above, I see the blueness and deepness of sky.

Below, I see the greenness and the restlessness of water….

Heaven is high, earth wide; bitter between them flies my sorrow.

Can I dream through the gateway, over the mountain?

Endless longing

Breaks my heart.

#### ENDLESS YEARNING II

The sun has set, and a mist is in the flowers;

And the moon grows very white and people sad and sleepless.

Would that it might follow the spring wind to Yanran Mountain.

Since nobody can bear to you the burden of my song,

I think of you far away, beyond the blue sky,

And my eyes that once were sparkling

Are now a well of tears.

… Oh, if ever you should doubt this aching of my heart,

Here in my bright mirror, come back and look at me!

This isn’t the best poetry I’ve seen, but it isn’t the worst. Parents, I understand, try to get children to write poetry all the time — mine certainly did — but it generally takes many years before the little bundle of joy stops shitting their diapers and decides to take on Robert Frost. I’ve spent maybe three hours of my time on this so far, and most of that was spent sorting out code issues.

#### THE HARD ROAD

I would cross the Yellow River, but ice chokes the ferry;

I would climb the Taihang Mountains, but the sky is blind with snow….

I would sit and poise a fishing-pole, lazy by a brook —

But I suddenly dream of riding a boat, sailing for the sun….

Journeying is hard,

There are many turnings —

Which am I to follow?….

I will mount a long wind some day, and break the heavy waves

And set my cloudy sail straight and bridge the deep, deep sea.

#### DOWN ZHONGNAN MOUNTAIN

Down the blue mountain in Feng district

You have found your home.

The wind is beating at us, beating at our ears,

And we see only the dark clouds;

We hear only the low wind rustling grasses

Under the quiet river;

And the farmers all are returning what they have,

Washing their fields and burning them.

The GPT2–117M model seems, to mine untrained eyes, to have picked up the ‘form’ of Tang poetry more efficiently. Some rote phrases are inevitable given how small this dataset is, but I’m surprised at how little there are. With a few careful cuts — a line pruned here and there — I can bring out the impression of one overarching emotion. I’m particularly proud of this:

### THE LAMENT OF THE ATTACKING EMPEROR

Soldiers are sent north to guard the City of Silk

And east to receive the rain from the Spears of Heaven.

The south runs its wall, the stars are rising,

And our footprints are three hundred miles away.

How can I bear to sweep them away?

A vanished river is forgotten by the people….

Who knows if it is still alive?

… Who knows if it ever was?

Those last two lines, I have to stress, are most definitely not mine.

There’s a man I keep coming back to whenever I see something like this, and that’s the chessmaster Gary Kasparov. Kasparov is possibly the greatest human chess player we have seen to date; from 1986 to 2005 he was the world’s best at the game.

In 1997, Kasparov was defeated by a machine — IBM’s Deep Blue. The move changed chess history [3], and I think — looking back — that’s really where the “human vs machine” fear really hit home. Ever since then, chessmasters — the human kind — have accepted getting thrashed by machines.

What did Kasparov do? Kasparov went away and made computer-aided chess work. He took human vs machine and made it human + machine. His thesis is in the title of his TED Talk — “Don’t fear intelligent machines; work with them” [4]. Today, some of the world’s most powerful players are cyborgs — combinations of human players and machine intelligence — and they are damned difficult to beat [5].

I believe in this human + machine philosophy. Over the next year or so, I’m going to be launching more little experiments along this line. Let’s get see where it gets us.

A friend of mine, a mathematician, recently posited to me that the role of poetry was capture intricate emotion; I countered by saying the role of poetry was to convey information through the ordering of words as much as the words themselves. But in both our arguments there was the implicit understanding that there was a poet, some creator with a sense of purpose, be it information or emotion. I wonder if we can have the same argument about this, or whether we have to start that argument again with several biases removed.

[1] [https://www.gwern.net/RNN-metadata#finetuning-the-gpt-2-small-transformer-for-english-poetry-generation](https://www.gwern.net/RNN-metadata#finetuning-the-gpt-2-small-transformer-for-english-poetry-generation)

[2] [https://openai.com/blog/better-language-models/](https://openai.com/blog/better-language-models/)

[3] [https://www.chess.com/article/view/deep-blue-kasparov-chess](https://www.chess.com/article/view/deep-blue-kasparov-chess)

[4] [https://www.ted.com/talks/garry_kasparov_don_t_fear_intelligent_machines_work_with_them?language=en](https://www.ted.com/talks/garry_kasparov_don_t_fear_intelligent_machines_work_with_them?language=en)

[5] [http://www.bbc.com/future/story/20151201-the-cyborg-chess-players-that-cant-be-beaten](http://www.bbc.com/future/story/20151201-the-cyborg-chess-players-that-cant-be-beaten)


