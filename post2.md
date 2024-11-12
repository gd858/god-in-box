# Qwen/Qwen2.5-Coder-32B-Instruct · Hugging Face

[permalink](http://reddit.com/r/LocalLLaMA/comments/1goz6gr/qwenqwen25coder32binstruct_hugging_face/)
by *Master-Meal-77* (↑ 504/ ↓ 0)

## Comments

##### This is crazy, a model between Haiku (new) and GTP4o! ⏤ by *and_human* (↑ 107/ ↓ 0)
├─ Now I don't know what is the business model of chatgpt-4o-mini after the release of qwen-2.5-coder-32B.

Hard to compete with something that is better, fast, and free, and can run on any 32GB macbook. ⏤ by *ortegaalfredo* (↑ 5/ ↓ 0)
├── Actually it's even better than that. You only really need around 18 GB for this model, hence why 3090/4090's are able to run it with 24GB VRAM. ⏤ by *Anjz* (↑ 2/ ↓ 0)
├─── Yes, just loaded the 4-bit MLX on a old Mac M1 32GB and it took exactly 18GB, at 9 tok/s, slow but useable. I don't think a 16GB Mac can take this model, but the 32 can do it no problem. ⏤ by *ortegaalfredo* (↑ 3/ ↓ 0)
├── 32GB in memory is still like only the top 10 percent of devices though? ⏤ by *Mark__27* (↑ 1/ ↓ 0)
├─── And only for newer apple desktop/laptops. For windows/linux users you'd need a 3090/4090 to utilize faster speeds. ⏤ by *Anjz* (↑ 2/ ↓ 0)
├── Maybe for the people who don't have a 32GB macbook? ⏤ by *AuggieKC* (↑ 1/ ↓ 0)
└────

##### Here's the GGUF [https://huggingface.co/Qwen/Qwen2.5-Coder-32B-Instruct-GGUF](https://huggingface.co/Qwen/Qwen2.5-Coder-32B-Instruct-GGUF) ⏤ by *and_human* (↑ 86/ ↓ 0)
├─ Horray the model I have been waiting for has been released! 

  
Now for the tests. ⏤ by *Any_Pressure4251* (↑ 17/ ↓ 0)
├─ I am seeking education:

Why are there so many 0001-of-0009 things?  What do those value-of-value things mean? ⏤ by *darth_chewbacca* (↑ 11/ ↓ 0)
├── The models are large - they get broken into pieces for downloading. ⏤ by *Thrumpwart* (↑ 28/ ↓ 0)
├─── this feels unnecessary unless you're using a weird tool

like, the typical advantage is that if you have spotty internet and it drops mid download, you can pick up where you left off more or less

but doesn't huggingface's CLI/api already handle this? I need to double check, but i think it already shards the file so that it's downloaded in a bunch of tiny parts, and therefore can be resumed with minimal loss ⏤ by *noneabove1182* (↑ 17/ ↓ 0)
├──── I agree. The max huggingface file is 50GB, and a q8 32b is going to be about 35gb. Breaking that 35gb into 5 slices is overkill when huggingface will happily accept the 35GB file individually. ⏤ by *SomeOddCodeGuy* (↑ 16/ ↓ 0)
├──── They used upload-large-folder tool for uploads, which is prepared to handle spotty network. I am not sure why they sharded GGUF, just makes it harder for non-technical people to get around what files they need to run the model, and might not support some pull-from-HF in easy-to-use UIs using llama.cpp backend. 
I guess Great Firewall is this terrible they opted to do this to remove some headache they were facing, dunno. ⏤ by *FullOf_Bad_Ideas* (↑ 5/ ↓ 0)
├───── It also just looks awful in the HF repo and makes it so hard to figure out which file is which :')


But even with your proposed use case, I'm pretty certain huggingface upload also supports sharding files.. I could be wrong, but I'm pretty sure part of what makes hf_transfer so fast is that it's splitting the files into tiny parts and uploading those tiny parts in parallel ⏤ by *noneabove1182* (↑ 8/ ↓ 0)
├───── China access to huggingface is speed limited so it's super slow to download and upload files ⏤ by *TheHippoGuy69* (↑ 1/ ↓ 0)
├────── How slow we're talking? ⏤ by *FullOf_Bad_Ideas* (↑ 0/ ↓ 0)
├── Grab Bartowskis. The way Qwen did these GGUFs makes my eyes bleed. The largest quant, q8, is well below the 50GB limit for huggingface, but they broke it into 5 files. That drives me up the wall lol

[https://huggingface.co/bartowski/Qwen2.5-Coder-32B-Instruct-GGUF/tree/main](https://huggingface.co/bartowski/Qwen2.5-Coder-32B-Instruct-GGUF/tree/main) ⏤ by *SomeOddCodeGuy* (↑ 25/ ↓ 0)
├── They wrote it in the description. They had to split the files as they were too big. To download them to a single file you either 1) download them separately and use the llama-gguf-split cli tool to merge then, or 2) use the Huggingface-cli tool. ⏤ by *and_human* (↑ 9/ ↓ 0)
├─── To big for what?? It seems they had to limit to below 8 GB per file, which is so small when you're working with language models. ⏤ by *my_name_isnt_clever* (↑ 4/ ↓ 0)
├─── How do you use models downloaded from git with Ollama? Is there a tool also? ⏤ by *badabimbadabum2* (↑ 3/ ↓ 0)
├──── Ollama can only pull non-sharded models. You'll have to download the model shards, merge them using Llama.cpp and then load the combined gguf file with Ollama. ⏤ by *Few_Painter_5588* (↑ 9/ ↓ 0)
├──── you can use the ollama CLI commands to pull from HF directly now, though I'm not 100% sure it works nicely with models split into parts

couldn't find a more official announcement, here's a tweet:

https://x.com/reach_vb/status/1846545312548360319

but basically ollama run hf.co/{username}/{reponame}:latest ⏤ by *noneabove1182* (↑ 9/ ↓ 0)
├───── click the size you want on the teams -&gt; click "run this model" (top right) -&gt; ollama. It'll give you the CLI commands to run ⏤ by *IShitMyselfNow* (↑ 5/ ↓ 0)
├───── Thats nice for smaller models I guess. But I have pulled 60GB llama guard and I dont know what should I do to it to get it working with Ollama. Havent yet found any step by step instructions. Kind of new to this all. The "official" Ollama models are in /usr/share/ollama/.ollama but this one model cloned from git ..is not in same format somehow.. ⏤ by *badabimbadabum2* (↑ 4/ ↓ 0)
├──── Alternatively \`ollama pull qwen2.5-coder\`. Use \`ollama pull qwen2.5-coder:32b\` if you want the big boy. ⏤ by *agntdrake* (↑ 3/ ↓ 0)
├───── I want llama-guard-vision and it looks to be not Ollama compatible ⏤ by *badabimbadabum2* (↑ 3/ ↓ 0)
├───── Ollama pull gave a manifest not found error. Ollama run did the job. ⏤ by *No-Leopard7644* (↑ 1/ ↓ 0)
├────── \`run\` does effectively a pull, so it should have been fine. Glad you got it pulled though. ⏤ by *agntdrake* (↑ 1/ ↓ 0)
├───── What is the size of the smaller one? ⏤ by *guesdo* (↑ 1/ ↓ 0)
├────── The default is 7b, but there is \`qwen2.5-coder:3b\`, \`qwen2.5-coder:1.5b\`, and \`qwen2.5-coder:0.5b\` plus all the different quantizations. ⏤ by *agntdrake* (↑ 1/ ↓ 0)
├── It's best practice to split large files into shards, so that way you don't get any wonkiness when downloading. ⏤ by *Few_Painter_5588* (↑ 3/ ↓ 0)
├── Now they have also uploaded same Q as one file option. ⏤ by *mtomas7* (↑ 1/ ↓ 0)
├─ which gguf version  to run on 4GB vram slot and 16GB ram, can you help me with this ? ⏤ by *Infinite-Calendar542* (↑ 2/ ↓ 0)
├── 3B Instruct. ⏤ by *Arkonias* (↑ 1/ ↓ 0)
├─ Which version is okay for 12gb VRAM 128gb RAM? ⏤ by *Reasonable-Plum7059* (↑ 1/ ↓ 0)
└────

##### "Here's a super intelligent coder for free"

The future is good. ⏤ by *ortegaalfredo* (↑ 34/ ↓ 0)
##### I picked a bad time to switch the OS on my server! ⏤ by *Pedalnomica* (↑ 29/ ↓ 0)
├─ lol ⏤ by *Healthy-Nebula-3603* (↑ 3/ ↓ 0)
└────

##### Wake up bartowski ⏤ by *hyxon4* (↑ 59/ ↓ 0)
├─ Whoops, fell asleep at the wheel on this one:

https://huggingface.co/bartowski/Qwen2.5-Coder-32B-Instruct-GGUF

https://huggingface.co/bartowski/Qwen2.5-Coder-14B-Instruct-GGUF

https://huggingface.co/bartowski/Qwen2.5-Coder-3B-Instruct-GGUF

https://huggingface.co/bartowski/Qwen2.5-Coder-0.5B-Instruct-GGUF

and as always they're also up on lmstudio-community :)

https://huggingface.co/lmstudio-community?search_models=2.5-coder ⏤ by *noneabove1182* (↑ 197/ ↓ 0)
├── Thank you for your service ❤️ ⏤ by *hyxon4* (↑ 53/ ↓ 0)
├── The man, the myth, the legend?!

I've been downloading your ggufs for ages now. Thanks so much for your efforts, it's really appreciated. ⏤ by *sleepydevs* (↑ 9/ ↓ 0)
├── maybe you can make a gguf conversion bot that converts every single new upload onto hf into gguf /s. ⏤ by *Pro-editor-1105* (↑ 9/ ↓ 0)
├─── haha i did recently make a script to help me find new models that i haven't converted, but by your '/s' i assume you know why i avoid that mass conversions ;) 

for others: there's a LOT of garbage out there, and while i could have thousands more uploads if i made everything under the sun, i prefer to keep my page limited in an attempt to both promote effort from authors (at least provide a readme and tag with what datasets you use..) and avoid people coming to my page and wasting their bandwidth on terrible models, mradermacher already does a great job of making sure basically every model ends up with a quant so I can happily leave that to him, I try to maintain a level of "curation" for lack of a better word ⏤ by *noneabove1182* (↑ 27/ ↓ 0)
├──── Maybe a r/LocalLLaMA webscraper that looks for huggingface links on highly upvoted posts, and which checks the post text / comments with an LLM as a sanity check? ⏤ by *JarJarBeatU* (↑ 4/ ↓ 0)
├───── Not a bad call, though I'm already so addicted to /r/localllama I see most of em anyways 😅 but an automated system would certainly reduce the TTQ (time to quant) ⏤ by *noneabove1182* (↑ 13/ ↓ 0)
├──── Quick question, if the model was released 6 hours ago how's it possible that your ggufs are 21 hour old? ⏤ by *OuchieOnChin* (↑ 4/ ↓ 0)
├───── I have early access :) perks of building a relationship with the Qwen team! just didn't wanna release until they were public of course ⏤ by *noneabove1182* (↑ 25/ ↓ 0)
├─── He *is* that conversion bot. ⏤ by *DeltaSqueezer* (↑ 12/ ↓ 0)
├── Thanks!  I'm having bad results, is anyone else?  It's not intelligently coding for me.  Also I said fuck it, and tried the snake game html test just to see if it's able to pull from known code examples, and its not even working at all, not even showing a snake.  Using the Q8 and also tried Q6\_KL.

For the record qwen 72b performs amazing for me, and smaller models such as codestral were not this bad for me, so I'm not doing anything wrong that i know of.  Using kobold cpp using same settings I use for qwen 72b.

Same issues with the q8 file here: [https://huggingface.co/Qwen/Qwen2.5-Coder-32B-Instruct-GGUF/tree/main](https://huggingface.co/Qwen/Qwen2.5-Coder-32B-Instruct-GGUF/tree/main)

Edit: the Q4\_K\_M 32b model is performing fine for me.  I think there is a potential issue with some of the 32b gguf quants?

Edit: the LM studio q8 quant is working as I would expect.  it's able to do snake and simple regex replacement examples and some harder tests I've thrown at it: [https://huggingface.co/lmstudio-community/Qwen2.5-Coder-32B-Instruct-GGUF/tree/main](https://huggingface.co/lmstudio-community/Qwen2.5-Coder-32B-Instruct-GGUF/tree/main) ⏤ by *LocoLanguageModel* (↑ 6/ ↓ 0)
├─── &gt; I think there is a potential issue with some of the 32b gguf quants?

Seems unlikely but i'll give them a look and keep an ear out, thanks for the report! ⏤ by *noneabove1182* (↑ 3/ ↓ 0)
├── Seeking education again.

What is the difference between "Instruct" on a model, and a model w/o the instruct? ⏤ by *darth_chewbacca* (↑ 7/ ↓ 0)
├─── in (probably) all cases, "Instruct" means that the model has been tuned specially for interaction (instruction following), so you can say things like "Give me a python function to sort a list of tuples based on their second value"

a base model on the other hand has not received this tuning, it's actually the model right before it undergoes instruction tuning. Because of this, it doesn't understand what it means to be given instructions by a user and then outputting the result, instead it only knows how to continue generation

to get a similar result with a base model, you'd instead prompt it with something like:


    # This function sorts a list of tuples based on their second value
    def tuple_sorter(items: List[tuple]): -&gt; List[tuple]
        

and then you'd let the model continue generating from there

that's also why you prefer base models for code completion, they excel when just providing a continuation of the prompt, rather than responding as an assistant ⏤ by *noneabove1182* (↑ 28/ ↓ 0)
├──── Ahh ok.  So it's the difference between saying "complete the following code" (w/o saying that) and saying "please generate for me code which does X"

I read in https://huggingface.co/lmstudio-community/Qwen2.5-Coder-32B-GGUF

&gt; This is a BASE model, and as such should be used for completion and generation, not chatting or instruct

Is there a difference between chatting and instruct?  Or is `chatting or instruct` two synonyms for talking to the AI ⏤ by *darth_chewbacca* (↑ 7/ ↓ 0)
├───── they are basically synonyms, some models do make the distinction between an instruct model and a chat model, but the basic premise is that in an instruct/chat model there will be a back and forth of some kind, either a prompt and a response, or a user and an assistant

on the other hand, in a base model, there's not concept of "roles", there's no user or assistant, just text that gets continued ⏤ by *noneabove1182* (↑ 11/ ↓ 0)
├───── In this context, chatting means just that, and 'instruct' means batch processing of datasets that uses an instruction style of prompting (and so needs an instruct model to implement). ⏤ by *JohnnyDaMitch* (↑ 3/ ↓ 0)
├── [Hi Bartowski](https://media4.giphy.com/media/l2YSgsunrP27ddQje/giphy_s.gif?cid=6c09b952s4m4z9vnyj7ofenu6enrjpmsm4qo4wnlpno4hm3j&amp;ep=v1_internal_gif_by_id&amp;rid=giphy_s.gif&amp;ct=g) ⏤ by *ForsookComparison* (↑ 2/ ↓ 0)
├─ Is bartowski the new TheBloke?  ⏤ by *LatentSpacer* (↑ 14/ ↓ 0)
├── Yes had been for a while now. For GGUF Bartowski is king ⏤ by *markosolo* (↑ 18/ ↓ 0)
├── For a while now. Hey Bartowski 👏✌️ ⏤ by *LoadingALIAS* (↑ 2/ ↓ 0)
└────

##### Here's my results asking it "center a div using tailwind" with the m4 max on the coder 32b:

total duration:       24.739744959s

load duration:        28.654167ms

prompt eval count:    35 token(s)

prompt eval duration: 459ms

prompt eval rate:     76.25 tokens/s

eval count:           425 token(s)

eval duration:        24.249s

eval rate:            17.53 tokens/s

low power mode eval rate: 5.7 tokens/s  
high power mode: 17.87 tokens/s ⏤ by *coding9* (↑ 20/ ↓ 0)
├─ fp16, gguf, which quant? m4 max 40gpu cores? ⏤ by *anzzax* (↑ 2/ ↓ 0)
├── From eval rate it’s q8 model ⏤ by *inkberk* (↑ 3/ ↓ 0)
├─── q4, 128gb 40gpu cores, default sizes from ollama! ⏤ by *coding9* (↑ 4/ ↓ 0)
├──── With 128gb ram you can afford to run the q8 version, which I highly recommend. I get 15 tokens/second on the m1 ultra and the m4 max should be similar or better.

On the surface you might not immediately see differences, but there's definitely some significant information loss on quants below q8, especially on highly condensed models like this one.

You should also be able to run the fp16 version. On the m1 ultra I get around 8-9 tokens/second, but I'm not sure the speed loss is worth it. ⏤ by *tarruda* (↑ 2/ ↓ 0)
├─── &gt; 128

With m1 ultra I run the q8 version at ~15 tokens/second ⏤ by *tarruda* (↑ 1/ ↓ 0)
├─ Can you test for a longer context, e.g 5000 tokens? It will reflect better normal use cases won’t it? ⏤ by *ptrgreen* (↑ 2/ ↓ 0)
├─ What is load duration? Is that a one time wait? ⏤ by *auradragon1* (↑ 1/ ↓ 0)
└────

##### Qwen models really do impress. I'm not even sure they have the same compute either as other players. I think the scarcity will actually force them to innovate beyond the gpu rich players. ⏤ by *race2tb* (↑ 36/ ↓ 0)
├─ Agreed on the impressive part, but they're backed by Alibaba Cloud - I guess it's safe to assume they're not exactly GPU poor :-) ⏤ by *nitefood* (↑ 37/ ↓ 0)
└────

##### Wow, even the 14B is close to 4o. ⏤ by *phenotype001* (↑ 15/ ↓ 0)
##### Blog post: [https://qwenlm.github.io/blog/qwen2.5-coder-family/](https://qwenlm.github.io/blog/qwen2.5-coder-family/) ⏤ by *and_human* (↑ 31/ ↓ 0)
##### Here we go boys! ⏤ by *instant-ramen-n00dle* (↑ 10/ ↓ 0)
##### For a 3090 q6 could be the sweet spotttt ⏤ by *Playful_Fee_2264* (↑ 13/ ↓ 0)
├─ The Q6 needs close to 27GB so a bit too much:

[https://huggingface.co/bartowski/Qwen2.5-Coder-32B-Instruct-GGUF](https://huggingface.co/bartowski/Qwen2.5-Coder-32B-Instruct-GGUF) ⏤ by *tmvr* (↑ 3/ ↓ 0)
├── Yah, Will look for 5... But hooping for exl2 quanta... ⏤ by *Playful_Fee_2264* (↑ 3/ ↓ 0)
├─ Looks like Q4_K_M or Q4_K_L is about the largest if you want to fit kv cache and a longer context. ⏤ by *ThatsALovelyShirt* (↑ 2/ ↓ 0)
├── Im ok with 32k tho but Will try with higher to see how It works ⏤ by *Playful_Fee_2264* (↑ 1/ ↓ 0)
└────

##### For anyone interested, I will have a full set of OpenVINO conversions available in my hf repo, Echo9Zulu, later this week. ⏤ by *Echo9Zulu-* (↑ 6/ ↓ 0)
##### I have gtx 1660 super and 16 gb ram, can you recommend which model to download? ⏤ by *Egypt_Pharoh1* (↑ 4/ ↓ 0)
├─ your situation is unfortunate

https://preview.redd.it/735qqvti9c0e1.png?width=286&amp;format=png&amp;auto=webp&amp;s=be5227dfec0b75475536a3a81ebdf6584069a771

probably just use the 7b q4,   
or experiment with running 14b or even low quant 32b, though speeds will be quite low due to ram speed bottleneck ⏤ by *visionsmemories* (↑ 9/ ↓ 0)
├── Is there a way to make it run on CPU? I have ryzen 3600. Sorry for my ignorance, I'm new to this. I'm using MIST with ollama, there are many models and like you said with terms like instruct, GGUF can you tell me the diffeence? and later how should I know if I can run this model or not ? ⏤ by *Egypt_Pharoh1* (↑ 1/ ↓ 0)
├─── [https://ollama.com/library/qwen2.5-coder/tags](https://ollama.com/library/qwen2.5-coder/tags)

16GB of system RAM + 6GB VRAM = 24GB total RAM but you also have to remember you're running an OS here...so realistically more like 20GB usable and you really want the model to be smaller than your VRAM to have good performance and some context.

In order to run the 32B model you're going to HAVE to use an IQ3 or IQ2 quant and a VERY limited context (4-8K). It's generally not a good idea to run coding LLMs at such a low quant, they don't work well when they're that dumb. I would suggest you look at the 14B (partially GPU offloaded using Q4) or 7B (fully GPU offloaded on Q4) models. ⏤ by *ConversationNice3225* (↑ 5/ ↓ 0)
├──── Thank you very much, I get it now 😊 ⏤ by *Egypt_Pharoh1* (↑ 2/ ↓ 0)
├─ 14B ⏤ by *RipKip* (↑ 3/ ↓ 0)
└────

##### Yeah! Got it running at 1 token per second on my M4 Max! (Very large prompt with about 5000 in, "sort this shit out") ⏤ by *SniperDuty* (↑ 4/ ↓ 0)
├─ Hahahahhaha ⏤ by *LoadingALIAS* (↑ 1/ ↓ 0)
└────

##### For fill in middle should I use base or instruct? ⏤ by *Just_Maintenance* (↑ 3/ ↓ 0)
├─ The blog post says they use base model for FIM:

&gt;Additionally, Qwen2.5-Coder-32B has demonstrated strong code completion capabilities on pre-trained models, achieving SOTA performance on a total of 5 benchmarks: Humaneval-Infilling, CrossCodeEval,  CrossCodeLongEval, RepoEval, and SAFIM.

https://preview.redd.it/ajhcifobsb0e1.png?width=2774&amp;format=png&amp;auto=webp&amp;s=5afe7dacc2bcbf51a5ec492a71d2e89275cfc30e ⏤ by *and_human* (↑ 8/ ↓ 0)
├─ Base ⏤ by *Medical-Response-142* (↑ 4/ ↓ 0)
├── Are you sure about that? this [https://www.reddit.com/r/LocalLLaMA/comments/1fuenxc/qwen\_25\_coder\_7b\_for\_autocompletion/](https://www.reddit.com/r/LocalLLaMA/comments/1fuenxc/qwen_25_coder_7b_for_autocompletion/) person says instruct works.

I personally tried both and I feel like Instruct works better. Base had a tendency to not end the lines it filled (for example it writes something like `variable = someObject.function(` , it doesn't close parentheses). ⏤ by *Just_Maintenance* (↑ -4/ ↓ 0)
├─── If it works with base, it will work with instruct too of course. But when you're not using the model to give answers to your prompts, like for auto complete, using the instruct model is only going to hurt the performance. ⏤ by *stddealer* (↑ 3/ ↓ 0)
├─── &gt; Base had a tendency to not end the lines it filled

Sometimes that happens with github copilot too. ⏤ by *tarruda* (↑ 3/ ↓ 0)
└────

##### I hope HF will soon add it in their Chat UI. ⏤ by *anonynousasdfg* (↑ 3/ ↓ 0)
##### @SD buddies don't forget to pull the 7b repo: https://huggingface.co/Qwen/Qwen2.5-Coder-7B-Instruct/commit/014013f208b0d052dcd0b62bf35efeb573322498

The smaller models all have different vocab sizes. ⏤ by *randomanoni* (↑ 2/ ↓ 0)
##### This is the happiest thing for me today, qwen2.5 coder rocks ⏤ by *Status_Contest39* (↑ 2/ ↓ 0)
##### I’ve run the 32b 4-bit using MLX on my M1 Pro and it’s 12-15/s. The 14b 4-bit was 30t/s.

It’s 4AM, so I haven’t had the time to look to deep, but something is different here. They’ve done something that changes the quality of coding responses on par, or likely better, than Sonnet 3.5, GPTo1-preview, and Haiku 3.5.

I don’t know what it is, but I like it. 

I’ll share MLXFast results tomorrow. I wiped my MacBook last night like a fool and need to fix homebrew, etc. 

Wish me luck. lol ⏤ by *LoadingALIAS* (↑ 2/ ↓ 0)
├─ Yes, answers seem better structured. Try it in 8bpp, it really shows what the model can do. ⏤ by *ortegaalfredo* (↑ 1/ ↓ 0)
└────

##### For code autocomplete should I use base or instruct version? Thanks!  ⏤ by *Only_Emergencies* (↑ 2/ ↓ 0)
├─ How do you use code autocomplete locally? ⏤ by *kenvenin* (↑ 1/ ↓ 0)
├── [continue.dev](https://www.continue.dev/) has a free plugin that lets you use ollama etc in vscode or jet brains complete with autocomplete ⏤ by *Baader-Meinhof* (↑ 2/ ↓ 0)
├─ How? ⏤ by *BrownDeadpool* (↑ 1/ ↓ 0)
└────

##### Let's fire up this beast! ⏤ by *ali0une* (↑ 1/ ↓ 0)
##### Qwen launched with awq gguf etc last time, let’s hope they continue ⏤ by *Enough-Meringue4745* (↑ 1/ ↓ 0)
##### Does anyone know if they will be posting a non-instruct version like they have for the 7B and 14B versions?

I see reference to the 32B base model on their blog but it’s not on HF (yet) as far as I can tell. ⏤ by *tmostak* (↑ 1/ ↓ 0)
├─ They are releasing non-instruct and instruct at the same time.

7b has been release a while a ago, but just got updated few days ago.

Unless you are talking about quantized GGUF, they only release instruct officially because that's what most people use.

You could find non-instruct GGUF in 3rd party repo or use GGUF My Repo / llama.cpp to convert it. ⏤ by *popiazaza* (↑ 3/ ↓ 0)
└────

##### It just write a functional Tetris game with openwebui artifacts and LMStudio server- bartowski/Qwen2.5-Coder-14B-Instruct-GGUF. **An Q4\_K\_S !!** NO special system prompts. Very nice to say the least :) ⏤ by *maxpayne07* (↑ 1/ ↓ 0)
##### As someone who is noob and dont know anything yet? Why is this good? How different it is from claude and chatgpt on coding? ⏤ by *darkwillowet* (↑ 1/ ↓ 0)
├─ Because you can run it in your computer no need for internet and dont need to send your data or prompts to claude or openai, so privacy. ⏤ by *dimensions2050* (↑ 3/ ↓ 0)
├── Yeah i get that. But im as king how good is it compared to the others.. 

Ive been trying to learn more about llms. Im not yet in the level where i understanding the charts. ⏤ by *darkwillowet* (↑ 1/ ↓ 0)
├─── Cant trust the charts. Best to take the questions that you have asked other llms before and test them with the new llm. Then decide for yourself, because people be hyping anything lately ⏤ by *dimensions2050* (↑ 2/ ↓ 0)
├─ &gt;  Why is this good?

Not sure if that is good, but imagine you have a computer that has a junior programmer trapped in it, and this programmer has access to a "blurry" snapshot of all the information on the internet, and can work 24/7.

&gt; How different it is from claude and chatgpt on coding?

Run offline without sending data to big tech. ⏤ by *tarruda* (↑ 1/ ↓ 0)
└────

##### Anyone have benchmarks between this, sonnet 3.5, and DeepSeek V2 Coder Lite? ⏤ by *Vegetable_Sun_9225* (↑ 1/ ↓ 0)
├─ The launch blog post has comparisons: https://qwenlm.github.io/blog/qwen2.5-coder-family/

According to benchmarks, the 32b model is on par with GPT4-o and slightly below 3.5 sonnet ⏤ by *tarruda* (↑ 2/ ↓ 0)
└────

##### Qwen-coder-2.5 32b model is now available in https://huggingface.co/chat/ ⏤ by *MoaD_Dev* (↑ 1/ ↓ 0)
##### Can this be run on a single 3090? ⏤ by *No_Cat8545* (↑ 1/ ↓ 0)
├─ Possibly yes if you use something like Q4. You won't be able to take advantage of big contexts though. ⏤ by *tarruda* (↑ 1/ ↓ 0)
├── 16k fill perfectly .. if I use fa then 32k or 64k should be ok as well ⏤ by *Healthy-Nebula-3603* (↑ 1/ ↓ 0)
├─ yes - I am using llamacpp with rtx 3090 , qwen 32b q4km , context 16k , getting 37 t/s ⏤ by *Healthy-Nebula-3603* (↑ 1/ ↓ 0)
└────

##### Noob advice, What should I run with a 7800xt, 32gb ram? ⏤ by *coralish* (↑ 1/ ↓ 0)
├─ max is 14b q4km version for you ⏤ by *Healthy-Nebula-3603* (↑ 2/ ↓ 0)
├── How so? Can you explain? ⏤ by *coralish* (↑ 1/ ↓ 0)
├─── 16 GB card  and you need minimum q4km version of the model. ⏤ by *Healthy-Nebula-3603* (↑ 1/ ↓ 0)
└────

##### I have the lmstudio-community/Qwen2.5-Coder-32B-Instruct-GGUF/Qwen2.5-Coder-32B-Instruct-Q3\_K\_L.gguf running, I have it linked to Cline but is godawful slow . any reccomenmdations. 

I have 32GB Ram - NVIDIA GeForce RTX 3060/PCIe/SSE2

16 × AMD Ryzen 7 3700X 8-Core Processor ⏤ by *jmwtac* (↑ 1/ ↓ 0)
├─ Подожди пока Qwen добавит пространство на hugging face (может уже) с Qwen2.5-Coder-32B. ⏤ by *Senior_Explanation35* (↑ 0/ ↓ 0)
└────

##### Эта модель в рисовании на питоне используя turtle для меня обошла даже O1.

У O1 и других моделей все объекты в сцене отдельные и не логичные, а тут прям шедевр.

Вот запрос:

используя python turtle нарисуй дом, солнце, деревья

Код от Qwen2.5-Coder-32B:

https://preview.redd.it/knrms5jl0i0e1.png?width=800&amp;format=png&amp;auto=webp&amp;s=14d2d5e8b47edd5e9ffc61b3610611222afb66cc ⏤ by *Senior_Explanation35* (↑ 0/ ↓ 0)
##### I am new here and still learning. Can someone please tell me why everyone is so excited for this? Is it good? ⏤ by *BrownDeadpool* (↑ 1/ ↓ 0)
├─ Очень хорошо ⏤ by *Senior_Explanation35* (↑ 1/ ↓ 0)
└────

##### Is it even worth getting like the q2 version? ⏤ by *Electronic_Tart_1174* (↑ 1/ ↓ 0)
├─ No ⏤ by *Master-Meal-77* (↑ 6/ ↓ 0)
├── Didn't think so. What's the use case for something like that? ⏤ by *Electronic_Tart_1174* (↑ 2/ ↓ 0)
├─── Better than nothing if that’s all you can run. ⏤ by *mrskeptical00* (↑ 1/ ↓ 0)
├──── I guess I'll have to figure that out.. i don't know if it'll be better than running another model at q8 ⏤ by *Electronic_Tart_1174* (↑ 1/ ↓ 0)
├───── I wouldn’t think so. ⏤ by *mrskeptical00* (↑ 3/ ↓ 0)
├────── Me neither, which is why i don't get what's the point of making a q2 version. ⏤ by *Electronic_Tart_1174* (↑ 1/ ↓ 0)
├─────── That's a very fair question. I think it's more useful on models focusing on roleplay and creative writing where you can get away with some brain damage. Especially very large models, over 70B ⏤ by *Master-Meal-77* (↑ 2/ ↓ 0)
├─ I think the general consensus is that coding models become pretty unreliable when heavily quantized. ⏤ by *GreatBigJerk* (↑ 2/ ↓ 0)
└────

##### ok now how do we get this to run with 1 bit inference so us poor folk can use it? ⏤ by *zono5000000* (↑ -6/ ↓ 0)
├─ Qwen2.5-Coder-14B is almost as good and it will run reasonably fast on any modern cpu. ⏤ by *ortegaalfredo* (↑ 6/ ↓ 0)
├─ if you are poor in gpu  and cpu use cloud instead .. ⏤ by *Healthy-Nebula-3603* (↑ 1/ ↓ 0)
└────

##### can't run on HF spaces. error:

403 Forbidden: None.
Cannot access content at: https://api-inference.huggingface.co/models/Qwen/Qwen2.5-Coder-32B-Instruct.
Make sure your token has the correct permissions.
The model Qwen/Qwen2.5-Coder-32B-Instruct is too large to be loaded automatically (65GB &gt; 10GB). Please use Spaces (https://huggingface.co/spaces) or Inference Endpoints (https://huggingface.co/inference-endpoints).


edit: it's up https://huggingface.co/spaces/llamameta/Qwen2.5-Coder-32B-Instruct-Chat-Assistant ⏤ by *balianone* (↑ -3/ ↓ 0)
##### Good job guys. Great achievement for open weight models.

But personally disappointed as I was looking for something good enough to save money on Sonnet, but this is not it, sighs, I'll stay paying hundreds a month to anthropic. ⏤ by *Charuru* (↑ -26/ ↓ 0)
├─ According to the charts on their blog post it's better than 3.5 Sonnet ⏤ by *Master-Meal-77* (↑ 13/ ↓ 0)
├── Hmm tbh I zero'ed in on Aider which is the one I trust the most and it loses by a big margin there. But looking at it again it wins on several other benchmarks, which is interesting. But some of those where it wins like BigCodeBench also has 4o beating Sonnet which makes no sense to me and makes me think weirdly of the bench. Maybe this is good enough for giving personal eval a try. ⏤ by *Charuru* (↑ -1/ ↓ 0)
├─── youre correct about their benchmarks being slightly missleading, but cmon man, you get a sota open weights coder model for precisely 0.0$ and the first thing you do is complain? 

i mean you do you, whatever makes you happy ⏤ by *visionsmemories* (↑ 6/ ↓ 0)
├──── No the first thing I did was congratulate and applaud them. ⏤ by *Charuru* (↑ 3/ ↓ 0)
├───── I understand but what it felt like was that you congratulated them and also complained for something that costs you nothing. It’s like a homeless person complaining about the house being given to him for free not being good enough ⏤ by *BrownDeadpool* (↑ 1/ ↓ 0)
└────

