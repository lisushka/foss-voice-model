# Building a speech-to-text model for use in captioning and transcribing technical conferences in Australia

## Project Leads

- [Matt Cengia](https://github.com/mattcen)
- [Dawn E. Collett](https://github.com/lisushka)
- [Kathy Reid](https://github.com/KathyReid)

## Background

Providing live captions and transcripts for talks is among the hardest accessibility problems for conference organisers.  We (Matt, Dawn, and Kathy) want to build an automated solution which is tailored to technical conferences.

In late 2021, PyCon AU brought Matt on to improve conference accessibility.  Matt contacted Dawn, who has significant experience with captioning talks for conferences, to discuss ways to encourage speakers to caption their talks.  Dawn's current captioning workflow, as of LCA 2022, can be found in [this repository](https://github.com/lisushka/caption-runbook).  Prior to LCA 2022, this workflow was approximately 50% proprietary; Dawn's initial goal was to convert this workflow to use only open-source tools and human intervention, so that it could be distributed to anyone wishing to caption or transcribe their talks for PyCon AU 2022.

After experiementing with open-source tools for generating captions using their own previous talks, Dawn asked Kathy about toolchains and datasets for training speech-to-text models on non-`en-US` accents.  The three of us then formed a working group to figure out whether and how a pre-trained model might improve the number of captioned talks at Australian tech conferences.

## What we know

- Most people who caption their own talks use at least some proprietary tools
- Apart from Dawn's attempt at documenting their workflow, there are few to no resources for computer-aided captioning using open-source tools (the best general resource is Meryl Evans' [**The Complete Guide to Captioned Videos**](https://meryl.net/captioned-videos-complete-guide/))
- Open voice datasets such as Common Voice rely heavily on recordings of public domain texts - they are good at recognising words like 'tenement' and 'good sir', but struggle with colloquial and technical language like 'I gave Gentoo the boot and started building Arch for fun'
- To build a model that's more likely to work for a variety of different people, our initial dataset will need to be diverse in the following attributes:
  - Accent
  - Age of the speaker
  - Vocal attributes (pitch/tone/resonance)
  - Speaking speed
  - Enunciation

## What we want to do

- Fill in as many of the gaps in Dawn's current captioning process as possible
- Try training a model ourselves, using ~100 hours of recorded talks from a range of speakers
- Test the model on other talks, and use the results to determine how much data we think we're going to need to produce an open-source speech-to-text model that's reliable enough to give to `en-AU` speakers seeking to caption technical videos
- Use this information to develop the full-scale model
- Share the model under a data trust, or other data governance structure which allows submitters to decide how the data can and cannot be used
- Investigate the possibility of using our model at Australian tech conferences, starting with the ones run by Linux Australia

## What we've decided

- We're going to build the model using [CoquiSTT](https://github.com/coqui-ai/STT), as it's the open-source toolchain with the best support
- We need to find a lawyer or law firm that has some experience with novel legal structures for data governance

## Where do you come in?

- We are currently searching for an Australian law firm with experience in setting up data trusts to quote for the legal work required - if you have this expertise, or know of a firm that does, please let us know [here](https://github.com/lisushka/foss-voice-model/issues/1)
- We are looking for two groups of volunteers:
  - People who have spoken at conferences before, and are willing to allow us to use the recordings in developing our initial model - go [here]()
  - People who are willing to help us with editing talk transcripts, and splitting up both audio files and transcripts so that CoquiSTT can handle them - go [here]()
