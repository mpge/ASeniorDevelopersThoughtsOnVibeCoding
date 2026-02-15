# A senior developers thoughts on Vibe Coding

I have been using Claude Code within my personal projects and at my day job for roughly a year. At first, I was skeptical. I have been coding since the ripe age of 12 (learning out of textbooks on my family road trips down to Florida), made my first dime at 14, took on projects at 16, and have had a development position since 18. I have more than 14 years of experience in development, and countless hours writing, reviewing, and maintaining large codebases. When I first used Claude Code, my first impression was, “this is game-changing.”

But I have been vocally concerned about “vibe coding.” Heck, I do it myself. I come up with prompts and watch as the AI magically pieces together bug fixes and feature requests. But the point is — I watch. I review.

Today at work, I was writing a feature with regard to CSV imports. While I can't release the code due to PI, I can detail an example below. When I asked to fix a unit test, I was thrown away.

What came up next was something that surprised even me upon review.


```
foreach ($rows as $row) {
// My modification function
$userId = $row['user_id'] ?? Auth::id();
$row = $this->modifyFunction($row);
// other stuff
}
```

This was an immediate red flag.

Based on this code, $userId would be setting which user this row belonged to. In this environment, the user would be charged.

If you've developed for even a short amount of time, you'd realize that allowing users to specify which user they are could probably lead to some security issues.

And Claude Code wrote it.

Claude Code relies heavily on training and past context. I can only presume that because CSV imports are very much an “admin feature,” Claude assumed.

It wasn’t.

Or, it was simply trying to "pass" my unit tests.

Because of my own due diligence, I was able to catch this and change it prior to it even being submitted for review.

But what if it hadn't? What if I had vibe coded this application and just assumed the AI knew what it was doing? What if I never took a split second to actually look at the code it was writing?

What if I trusted the AI?

We've been inundated with companies marketing AI development as “anybody can do it.”

And while that quite literally is true — ANYBODY can learn to become a developer. Heck, the opportunities have never been better.
That does not mean ANYBODY can be a developer without learning.
Don't be fooled by the large AI companies selling you this dream. I would bet my last dollar that deep within their Terms of Service, their liability and warranty end the minute you press enter.

The reality is, every senior developer got to being a senior developer - through mistakes, and time. Through lessons hard taught, and code that - 5 years later - you cringe reading (I still keep my old github repos alive & private for this reason).

The problem is - vibe coding, without review, removes this. It removes the teaching of your brain to "think like a developer". To think of every possible outcome, every edge case. It removes your ability to learn - IF you chose for it to.

My recommendations for any junior developer, or someone seeking to go into development would be the follows.

## Learn off the vibe code. Don't just read it, understand it.

The code AI writes, 95% of the time, is impressive. Learn from it. Try to understand the algorithmic logic behind. Try to understand what it's trying to accomplish, how it could be done differently (if you wanted to). Try to think "Why did Claude write it, the way it did".

Don't launch a vibe coded app, that handles vital information - without checking it.

I have seen far too many apps launched, and dismantled within hours. Heck, I've argued with folks on LinkedIn who claimed their "AI powered support SaaS" is 100% secure because, "AI is much better and will always be better at security, than humans are".

Don't be that guy or gal.

I like to think of the AI as a junior developer, who is just really crazy fast at typing. They are very intelligent, but they're prone to mistakes.

## Get rid of the ego:

If you just installed Claude Code, and have never touched a line of code in your life. You are NOT a developer -- yet. That is perfectly OK. We all start somewhere, and that does not mean you have to "wait" to become a developer. AI is one of the most powerful advancements in development we've seen to date. It personally has made me 10x more productive (and other senior developers alike).

Probably 95% of the code I write has been AI generated. But the other 5% written by the AI, was abysmal.

The point is not to assume the AI knows everything. Don't assume you do either. Learn, and treat every line of code as if it's trying to take away your newborn.

You can trust, but verify.

## Understand that with time, you'll understand more. And you'll be a hell of a lot better at watching the AI do it's thing.

Half the time when I'm vibe coding, I have my hand on the Shift-Tab and Esc button like my life depends on it. It doesn't take me long before I stop, say "Try this approach instead" and the AI continues on it's merry way like they didn't just try to destroy the app I built.

I like to use this comparison when it comes to using AI.

Just because I pick up a guitar, doesn't mean I can hop on stage in front of a 1000 person concert.

People who have been playing guitar for 10+ years (or professional), can hear a song, probably identify the chords, the key it's played in, and probably serve an amazing rendition of it right on the spot (or drums -> https://www.youtube.com/watch?v=HMBRjo33cUE)

People who have played guitar for a year or so, will probably look up the chords, and still do a pretty damn good job.

People who have never played guitar a day in their life, will pickup the guitar, strum loosely to the music, and somewhat get the jist.

But you can't take the person who just picked up the guitar, and put him or her in front of a large audience. It wouldn't work.

Think the same, of the apps you are building. You are effectively, doing the same thing.
With a caveat,

You can be that rockstar. You can launch that app that serves thousands, if not millions of people. Heck you can make a damn lot of money.

But learn. Learn in the process. Understand the code. Understand the risks. Always, Trust but Verify.
