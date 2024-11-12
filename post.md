# Qwen-2.5-Coder 32B – The AI That's Revolutionizing Coding! - Real God in a Box?

I just tried Qwen2.5-Coder:32B-Instruct-q4\_K\_M on my dual 3090 setup, and for most coding questions, it performs better than the 70B model. It's also the best local model I've tested, consistently outperforming ChatGPT and Claude. The performance has been truly god-like so far! Please post some challenging questions I can use to compare it against ChatGPT and Claude.

Qwen2.5-Coder:32b-Instruct-Q8\_0 is better than Qwen2.5-Coder:32B-Instruct-q4\_K\_M

Try This Prompt on **Qwen2.5-Coder:32b-Instruct-Q8\_0**:

&gt;Create a single HTML file that sets up a basic Three.js scene with a rotating 3D globe. The globe should have high detail (64 segments), use a placeholder texture for the Earth's surface, and include ambient and directional lighting for realistic shading. Implement smooth rotation animation around the Y-axis, handle window resizing to maintain proper proportions, and use antialiasing for smoother edges.  
Explanation:  
Scene Setup : Initializes the scene, camera, and renderer with antialiasing.  
Sphere Geometry : Creates a high-detail sphere geometry (64 segments).  
Texture : Loads a placeholder texture using THREE.TextureLoader.  
Material &amp; Mesh : Applies the texture to the sphere material and creates a mesh for the globe.  
Lighting : Adds ambient and directional lights to enhance the scene's realism.  
Animation : Continuously rotates the globe around its Y-axis.  
Resize Handling : Adjusts the renderer size and camera aspect ratio when the window is resized.

Output :

[Three.js scene with a rotating 3D globe](https://i.redd.it/bs2q2dnfbh0e1.gif)

Try This Prompt on **Qwen2.5-Coder:32b-Instruct-Q8\_0**:

&gt;Create a full 3D earth, with mouse rotation and zoom features using three js  
The implementation provides:  
• Realistic Earth texture with bump mapping  
• Smooth orbit controls for rotation and zoom  
• Proper lighting setup  
• Responsive design that handles window resizing  
• Performance-optimized rendering  
You can interact with the Earth by:  
• Left click + drag to rotate  
• Right click + drag to pan  
• Scroll to zoom in/out

Output :

[full 3D earth, with mouse rotation and zoom features using three js](https://i.redd.it/3dul8v6jgh0e1.gif)

[permalink](http://reddit.com/r/LocalLLaMA/comments/1gp84in/qwen25coder_32b_the_ai_thats_revolutionizing/)
by *Vishnu_One* (↑ 381/ ↓ 0)

## Comments

##### I’m running q5_k_m on my m4 max MacBook Pro with 128GB RAM (22.3GB model size when loaded). 11.5t/s in LM Studio with a short prompt and 1450 token output. Way too early for me to compare vs sonnet for quality
Edit: 22.7t/s with q4 MLX format ⏤ by *thezachlandes* (↑ 90/ ↓ 0)
├─ 11.5t/s is Very good! for a laptop ⏤ by *Vishnu_One* (↑ 29/ ↓ 0)
├── Kinda crazy that you can have GPT4 qualify for programming in a frickin consumer laptop. Who knew that programming without internet access is the future 😂 ⏤ by *satireplusplus* (↑ 11/ ↓ 0)
├─── Original gpt4 is far more worse  .

We have a bit better than GPT4o open source model now.

Look I created galaxian game with qwen coder 32b in 5 min iterating by adding nicely flickering stars, color transitions etc

https://preview.redd.it/kcxj6h17bh0e1.png?width=805&amp;format=png&amp;auto=webp&amp;s=aa39bb37c2b3279fd14cc0167b94280484fae20d ⏤ by *Healthy-Nebula-3603* (↑ 5/ ↓ 0)
├── Agreed. Very usable! ⏤ by *thezachlandes* (↑ 9/ ↓ 0)
├─── I get over 17 with the q4 on my m4 max ⏤ by *coding9* (↑ 8/ ↓ 0)
├──── Q: how do you know somebody has an m4 max? A: they tell you. ⏤ by *KeyPhotojournalist96* (↑ 40/ ↓ 0)
├───── When they spend that much money they need to let you know. ⏤ by *rorowhat* (↑ 6/ ↓ 0)
├───── I hate this comment.
Local is in its infancy, we are comparing many kinds of hardware. Stating the hardware is helpful. ⏤ by *jxjq* (↑ 3/ ↓ 0)
├────── That's true.

  
\-Sent from my Iphone 23 plus PRO deluxe black edition Mark II 128gb ddr8 (MUCH BETTER THAN THE PLEB MACHINE 64gb) ⏤ by *oodelay* (↑ 2/ ↓ 0)
├──── I just tried the MLX q4 and got 22.7! ⏤ by *thezachlandes* (↑ 2/ ↓ 0)
├───── Any guide how to set it up with mlx? ⏤ by *ahmetegesel* (↑ 1/ ↓ 0)
├────── Just download LMStudio for Mac. In the models page, search for MLX Qwen2.5 32B coder. You’ll see the one from MLX community. Download and load the model. Open a chat. ⏤ by *thezachlandes* (↑ 8/ ↓ 0)
├────── Two ways: first see if there is already a conversion on HuggingFace MLX community. If there isn’t, doing your own conversions is surprisingly easy and fast, and there’s instructions for how to do it on HF MLX community page. One tip is to delete the original files once they’re converted because they are huge. ⏤ by *GimmePanties* (↑ 2/ ↓ 0)
├─────── I am a bit paranoid to install lm studio because it is not open source. And mlx own server seems a bit trivial to run/load the models. Do you happen to know an alternative open source way that is easy to swap models as well? ⏤ by *ahmetegesel* (↑ 1/ ↓ 0)
├────── LM Studio supports mlx download and inference natively. Easy peasy. ⏤ by *Thrumpwart* (↑ 2/ ↓ 0)
├────── Also interested ⏤ by *mcdougalcrypto* (↑ 1/ ↓ 0)
├─ Try the mlx quants. You'll get much higher throughput ⏤ by *NoConcert8847* (↑ 11/ ↓ 0)
├── Hey thank you, I didn’t see they were released! With q4 I got 22.7 t/s! ⏤ by *thezachlandes* (↑ 16/ ↓ 0)
├── does ollama automatically get this?

https://ollama.com/library/qwen2.5-coder:32b ⏤ by *Tomr750* (↑ 2/ ↓ 0)
├─── Yep ⏤ by *CheatCodesOfLife* (↑ 3/ ↓ 0)
├─ Just to share some test results for MLX format on M2/3 Max:

M2 Max 12/30

4 bit: 17.1 t/s

8 bit: 9.9 t/s


M3 Max 14/30 (performance ~ M4 Pro 14/20)

High Power

4 bit: 13.8 t/s

8 bit: 8 t/s


Low Power

4 bit: 8.2 t/s

8 bit: 4.7 t/s ⏤ by *Durian881* (↑ 4/ ↓ 0)
├─ It should work fine with the 48gb version right ? ⏤ by *matadorius* (↑ 2/ ↓ 0)
├─ Did you get the MLX format working on LMStudio? ⏤ by *adrenoceptor* (↑ 3/ ↓ 0)
├── Yes. MLX community organization ⏤ by *thezachlandes* (↑ 6/ ↓ 0)
├─ What's your time to first token, would you say?  
Also, can you try a bit higher Q, like Q6 or Q8?

Thanks. ⏤ by *CBW1255* (↑ 1/ ↓ 0)
├─ What’s Max context? My m4 arrives today with same amount of ram and giddy with excitement.  ⏤ by *EFG* (↑ 1/ ↓ 0)
├─ What does the k_m vs k_s mean? I only have a p100 currently so I can't use the m purely in Vram. ⏤ by *Thetitangaming* (↑ 1/ ↓ 0)
├─ Cries in 18GB M3 Pro ⏤ by *ajunior7* (↑ 1/ ↓ 0)
├─ This is an awesome datapoint, thanks. Could you try running the big boy q8 and see how much performance changes?

I'm also super interested in how performance changes with large context (128k) as it fills up. I'm trying to determine if 128GB of RAM is overkill or ideal. Does the tok/s performance of models that need close to the full RAM become unusably slow? The calculator says the q8 model + 128k context should need around 75GB of total VRAM. ⏤ by *gnd* (↑ 1/ ↓ 0)
├─ Do you guys just run the models on host computer or do some sort of VM ? Even though it’s all local I’m still trying to do some isolation ⏤ by *Psychedelic_Traveler* (↑ 1/ ↓ 0)
├── No VM. I’m curious, why do you need more isolation? VMs for computer use agents so they can’t mess up the host? ⏤ by *thezachlandes* (↑ 3/ ↓ 0)
├── I have not been letting my AI run rampant, but if you're trying to get it to write and rewrite code on it's own or use your computer I can see why you want a VM. I think they're not too hard to use, depends on your system. I've heard good things about Qemu but haven't tried it and it was a long time ago someone recommended it. It's a generic virtual machine that works across platforms. But so far I only use the AI for simple call and response and then copy and paste the code so there's no way it'll mess up my computer. Unless of course I don't look at the code at all and just plop it in, then I guess anything could happen lol. ⏤ by *Low_Poetry5287* (↑ 1/ ↓ 0)
├─ What's the ram usage of the q4? Will the M4 Pro 48GB be enough? ⏤ by *gopietz* (↑ 1/ ↓ 0)
├── I believe it’s 18GB. So, yes, you’ve got enough RAM ⏤ by *thezachlandes* (↑ 2/ ↓ 0)
├─ deleted 
└────

##### Is it outperforming GPT-4.0 (ChatGPT paid version) for your needs? ⏤ by *TheDreamWoken* (↑ 15/ ↓ 0)
├─ On the aider leaderboard, it is consistently better than GPT-4o, but cannot beat OpenAI o1 yet. ⏤ by *CNWDI_Sigma_1* (↑ 8/ ↓ 0)
├── Correct me if I’m wrong but O1 is just a technique right and the model is still 4o right? Can’t we just upgrade Qwen 32B coder in the future with the same technique that was used to build O1? ⏤ by *HeftyCarrot7304* (↑ 3/ ↓ 0)
├─── OpenAI said it is another model specifically trained to use CoT ⏤ by *bolmer* (↑ 6/ ↓ 0)
├──── Bro I can also say Llama 3.2 is a different model specifically trained to be more accurate. I mean you never know with these corporate speeches. ⏤ by *HeftyCarrot7304* (↑ 5/ ↓ 0)
├─── Is the model itself retrained on the CoT technique in its training data or is o1 just a system prompt/agent-orchestrator? ⏤ by *2016YamR6* (↑ 1/ ↓ 0)
├──── OpenAI said it's another model trained specifically to use CoT ⏤ by *bolmer* (↑ 2/ ↓ 0)
├──── deleted 
├─── O1 knowledge cutoff went backwards. So it's probably using multiple GPT3s or similar.  ⏤ by *Agitated_Space_672* (↑ 1/ ↓ 0)
├──── I checked and Qwen and o1 have similar knowledge cutoffs. My guess is that the ETL processes to generate training data are as if not more expensive and also expansive requiring efforts from massive teams to get right. This is why most models are currently trying to squeeze as much juice as possible from modifying Transformer algorithms here and there. ⏤ by *HeftyCarrot7304* (↑ 1/ ↓ 0)
├─── It's a "model". It's fine-tuned 4o and we all know that model is not SOTA. If another org did the same thing with their better models, it would have better results. So saying o1 is the best feels misleading.

(Also these names are so bad OpenAI, why do you do this) ⏤ by *my_name_isnt_clever* (↑ 1/ ↓ 0)
└────

##### You are saying your questions are simple enough to not need a larger quant than Q4, yet you said it consistently outperforms gpt4o AND Claude. Care to share a few examples of those outperformances? ⏤ by *Qual_* (↑ 53/ ↓ 0)
├─ deleted 
└────

##### Write a web application for SRM (Supplier Relationship Management) in Python by using FastAPI and DDD (Domain-Driven Design) approach. Utilize the full DDD toolkit: aggregates, entities, VO (Value Objects), etc. Use SQLAlchemy as ORM and Repositories + UOW patterns. ⏤ by *Additional-Ordinary2* (↑ 30/ ↓ 0)
├─ [https://pastebin.com/rL2TQBsQ](https://pastebin.com/rL2TQBsQ) ⏤ by *Vishnu_One* (↑ 45/ ↓ 0)
├── That's just useless boilerplate code. Most ide's have templates that can do this... Maybe for hobby projects but not in a professional setting. ⏤ by *Noiselexer* (↑ 10/ ↓ 0)
├─── While I agree with this, a good boilerplate generation isn't useless, as it does save you some time. ⏤ by *Llamanator3830* (↑ 3/ ↓ 0)
├── And did it run correctly? ⏤ by *ScoreUnique* (↑ 3/ ↓ 0)
├─── Not really ⏤ by *Additional-Ordinary2* (↑ 3/ ↓ 0)
└────

##### I see so many folks here asking how to run it on xyz, just do I what I do and use openrouter, cost per million tokens is like 0.2$, it's rediculously affordable, I used to use claude sonnet 3.5 but this just blows it out of the water with the value it has at that price ⏤ by *Feeling-Currency-360* (↑ 7/ ↓ 0)
├─ [https://huggingface.co/chat/](https://huggingface.co/chat/) has it for free. Im using their API which is free for now. So far its pretty good. ⏤ by *Illustrious-Lake2603* (↑ 3/ ↓ 0)
├── The difference is in the context size? ⏤ by *Critical__Hit* (↑ 2/ ↓ 0)
├─ When you say per million token, does each request cost .2 cents or does it aggregate multiple request until I reach a million and only the it charges me?

This looks so much affordable compared to me finding two 3090s to play with this model. ⏤ by *LanguageLoose157* (↑ 1/ ↓ 0)
├── Say my prompt + output is total 100k tokens, then it's 0.02 cost, you preload money onto openrouter and it subtracts after each prompt essentially ⏤ by *Feeling-Currency-360* (↑ 1/ ↓ 0)
├── seems like it should run in a single 3090 @ q4 ⏤ by *BasicBelch* (↑ 1/ ↓ 0)
└────

##### 32gb is a nice compact size. I may pull the trigger on a 48gb mac mini pro. 

Can someone validate if this will run on 48gb m4 with ok performance? ⏤ by *whatthetoken* (↑ 7/ ↓ 0)
├─ It will run okay if you use the 8bit quantized model. fp16 will probably be quite unusably slow. Regardless, it won’t be close to speeds you get from hosted LLMs.

If you plan on buying it just for this, I don’t recommend it. The model by virtue of its size will have bad ‘reasoning’, and you will need to be quite precise with prompting. Even if it’s amazing at generating ‘good’ code.

This is amazing for people who already have the infrastructure. ⏤ by *SnooRabbits5461* (↑ 1/ ↓ 0)
└────

##### &gt; Qwen2.5-Coder:32B-Instruct-q4_K_M

Can you measure the RAM usage? Does it support RAM offload? ⏤ by *asteriskas* (↑ 12/ ↓ 0)
├─ [deleted] ⏤ by *[deleted]* (↑ 12/ ↓ 0)
├── I also have a 3090, but I only get 27t/s... any clue what could be such a huge difference?

Although that was with 2.5 instruct, not coder instruct.  Maybe the coder is faster now? ⏤ by *phazei* (↑ 2/ ↓ 0)
├─── Only! ⏤ by *Any_Pressure4251* (↑ 2/ ↓ 0)
├─── I'm using llamacpp...maybe it is faster.

Queen 32b instruct q4km context 16k ⏤ by *Healthy-Nebula-3603* (↑ 1/ ↓ 0)
├─── Your range is in the expected t/s though for llamacpp on a 3090, so don't sweat it. The best way to use your card to the full potential is batching a ton of request instead. ⏤ by *fiery_prometheus* (↑ 1/ ↓ 0)
├── awyisss ⏤ by *MusicTait* (↑ 1/ ↓ 0)
├─ \-----------------------------------------------------------------------------------------+

| NVIDIA-SMI 560.35.03              Driver Version: 560.35.03      CUDA Version: 12.6     |

|-----------------------------------------+------------------------+----------------------+

| GPU  Name                 Persistence-M | Bus-Id          Disp.A | Volatile Uncorr. ECC |

| Fan  Temp   Perf          Pwr:Usage/Cap |           Memory-Usage | GPU-Util  Compute M. |

|                                         |                        |               MIG M. |

|=========================================+========================+======================|

|   0  NVIDIA GeForce RTX 3090        On  |   00000000:02:05.0 Off |                  N/A |

|  0%   47C    P8             16W /  240W |   21659MiB /  24576MiB |      0%      Default |

|                                         |                        |                  N/A |

\+-----------------------------------------+------------------------+----------------------+

|   1  NVIDIA GeForce RTX 3090        On  |   00000000:02:06.0 Off |                  N/A |

|  0%   46C    P8              8W /  240W |       4MiB /  24576MiB |      0%      Default |

|                                         |                        |                  N/A |

\+-----------------------------------------+------------------------+----------------------+



\+-----------------------------------------------------------------------------------------+

| Processes:                                                                              |

|  GPU   GI   CI        PID   Type   Process name                              GPU Memory |

|        ID   ID                                                               Usage      |

|=========================================================================================|

|    0   N/A  N/A      7343      C   ...unners/cuda\_v12/ollama\_llama\_server          0MiB |

\+-----------------------------------------------------------------------------------------+











I think it's using a single GPU for Q4 ⏤ by *Vishnu_One* (↑ 5/ ↓ 0)
├── Indeed, using ~21.1Gb on the single GPU. ⏤ by *asteriskas* (↑ 7/ ↓ 0)
├─── So it might work with just one 3090 (I only have 1)? ⏤ by *NaiRogers* (↑ 2/ ↓ 0)
├──── Just tried this and it works fine, also Continue ⏤ by *NaiRogers* (↑ 1/ ↓ 0)
├── guess it depends on your setup, for me in LM Studio by default it seems to 50/50 split anything across both cards, i know in other stuff you can choose how much you offload to each card of course its just that LM Studio is just nice and simple to use

though out of interest how come your 3090s peak out at 250w? mine maxes at like 420w?

=========================================+======================+======================|

|   0  NVIDIA GeForce RTX 3090        Off | 00000000:02:00.0  On |                  N/A |

| 55%   38C    P2             112W / 420W |  18234MiB / 24576MiB |      4%      Default | ⏤ by *gaspoweredcat* (↑ 3/ ↓ 0)
├─── Default is 350, I set 240 to save power. ⏤ by *Vishnu_One* (↑ 5/ ↓ 0)
├─── lot of people cap the max usage of GPU to save power, since the main bottleneck is VRAM. so you are basically using the card for the VRAM and dont care much for GPU computing power.

Your 420W is a mis-reading. This is known in smi. the  3090 is rated for 350W. anything above it is a mis-read. ⏤ by *yhodda* (↑ 4/ ↓ 0)
├─ i used it to write an app for that ⏤ by *gaspoweredcat* (↑ 1/ ↓ 0)
└────

##### It even performs as good as if not better than other local models I've tried on my personal translation task (technical Japanese to English) which requires complicated instruction following (hf.co/bartowski/Qwen2.5-Coder-32B-Instruct-GGUF:IQ4_XS).  Impressive results for a coding model in a non-coding task. ⏤ by *condition_oakland* (↑ 6/ ↓ 0)
├─ I'm also working on a project where I translate Japanese texts into English. Could you tell me more about what you're currently working on? Maybe we could exchange ideas. ⏤ by *Rich_Number522* (↑ 1/ ↓ 0)
└────

##### This model is now available in https://huggingface.co/chat/ ⏤ by *MoaD_Dev* (↑ 6/ ↓ 0)
##### It is currently 5th place on Aider leaderboard, above GPT-4o, but slightly worse than old Claude Sonnet 3.5 and o1, and quite worse than new Claude Sonnet 3.5.

Still, it is absolutely impressive, and shows the performance never seen before with local models. Too bad it doesn’t support aider’s diff formats yet. ⏤ by *CNWDI_Sigma_1* (↑ 7/ ↓ 0)
├─ The 32b model can achieve this effect. It is really a breakthrough change. At least it can make us have very optimistic expectations for the performance improvement of open source models. ⏤ by *Front-Relief473* (↑ 5/ ↓ 0)
└────

##### I already using it in a massive code-scaffolding project with great results:

1. I get &gt;250 tok/s using 4x3090 (batching)
2. Sometimes it randomly switch to chinese. It still generates valid code, but start commenting in chinese, it's hilarious, it don't affect the quality of the code.
3. Mistral-Large-123B is still much better at role-playing, and other non-coding tasks. I.E. Mistral is capable of simulated writing in many local dialects, that Qwen-32B just ignores. ⏤ by *ortegaalfredo* (↑ 6/ ↓ 0)
├─ I'd imagine mistral large is just trained on a wider range of data. You could try finetuning qwen on dialects and see how well it works ⏤ by *fiery_prometheus* (↑ 1/ ↓ 0)
└────

##### \- 10x cheaper than gpt-4o (on openrouter) and quite on-par at some problems, pretty cool. (I get \~22t/s there)  
\- Locally, 9.5t/s on m1 max 64gb for the q8 quant.

\- Does not seem politically censored, can be quite critical of the chinesse government, as well as other government bc they all suck so it's fine. ⏤ by *shaman-warrior* (↑ 12/ ↓ 0)
##### "It's also the best local model I've tested, consistently outperforming ChatGPT and Claude."  
Why do you call it best LOCAL model then? ⏤ by *BobbyBronkers* (↑ 5/ ↓ 0)
├─ deleted 
└────

##### https://preview.redd.it/dg967pbxbh0e1.png?width=805&amp;format=png&amp;auto=webp&amp;s=32a1699f135323c8a44cac6cee21ed4a9426dbb6

qwen 32b q4km

Iterating few times to make galaxian game 

Iterating:

\--------------------------------------------------------------------------

Provide a complete working code for a galaxian game in python.

(code)

 \--------------------------------------------------------------------------

Can you add end game screen and "play again" feature? 

(code)

 \--------------------------------------------------------------------------

Working nice!

Can you reduce the size of enemies 50% and change the shape of our ship to a triangle?

(code)

 \--------------------------------------------------------------------------

A player ship is a triangle shape but the tip of the triangle is on the bottom, can you make that a tip of triangle to be on the top? 

(code)

 \--------------------------------------------------------------------------

Another problem is when I am shooting into enemies I have to shoot few times to destroy an enemy. Is something strange with hitboxes logic. 

(code)

 \--------------------------------------------------------------------------

Can you move "score" on top to the center ?

(code)

 \--------------------------------------------------------------------------

Can you add a small (1 and 2 pixel size) flickering stars in the background?

(code)

 \--------------------------------------------------------------------------

size = star\_sizes\[i\]   error      list index out of range   
(code)

 \--------------------------------------------------------------------------

Can you make enemies in the shape of hexagons and should changing colors invidually from green to blue gradually in a loop.  
(code)

 \--------------------------------------------------------------------------



Everything is working!

Full code here with iteration 

[https://ctxt.io/2/AAB4ol-iEA](https://ctxt.io/2/AAB4ol-iEA) ⏤ by *Healthy-Nebula-3603* (↑ 5/ ↓ 0)
##### Vllm will likely host it better im moving to it soonish from
Ollama ⏤ by *fasti-au* (↑ 8/ ↓ 0)
├─ Vllm absolutely smashes llama.cpp in speed ⏤ by *Enough-Meringue4745* (↑ 6/ ↓ 0)
├── Does LM Studio use Vllm behind the scene?
I do know Ollama uses llama.cpp (unless it has changed recently) ⏤ by *LanguageLoose157* (↑ 2/ ↓ 0)
├─── LM Studio is also llama.cpp based ⏤ by *Tannenbaumxy* (↑ 1/ ↓ 0)
├── How does it do in partial offload? I've noticed that they added that recently ⏤ by *MoffKalast* (↑ 1/ ↓ 0)
├─── My experience is that if you need vllms ability to batch it definitely works well even if you offload. ⏤ by *fiery_prometheus* (↑ 1/ ↓ 0)
├─ It was quite difficult for me to run it last time. Ollama is very easy to use. I will give it another try soon. ⏤ by *Vishnu_One* (↑ 2/ ↓ 0)
├── Yep it’s a when I get time thing here too hehe ⏤ by *fasti-au* (↑ 2/ ↓ 0)
├─ Is there a good front end to vllm? ⏤ by *rorowhat* (↑ 1/ ↓ 0)
├─ Just out of interest - are there any good guides for getting vLLM working? I've set up a proxmox server and webUI to deal with most of my AI stuff and I have absolutely no clue where to even start with making vLLM do something similar. Still fairly new to this, but the documentation for vLLM is a bag of shit as far as I can find. ⏤ by *OrdoRidiculous* (↑ 1/ ↓ 0)
└────

##### So I'm running 14b iq4_xs. 

I have 32gb ram and 8gb vram. 

Is that the best option? ⏤ by *Elegast-Racing* (↑ 3/ ↓ 0)
├─ For me prompt processing is very slow, with all the model loaded into VRAM ⏤ by *murlakatamenka* (↑ 1/ ↓ 0)
└────

##### Sorry if this is a dumb question but can a Mac M1 run it? ⏤ by *short_snow* (↑ 2/ ↓ 0)
├─ I can run it on my M1Max64/32. It works. I have also tried Supernova which a variant of it. ⏤ by *808phone* (↑ 2/ ↓ 0)
├─ Just testing  have M1 and 32 GB and it works kinda slow but definitely usable, ⏤ by *Atupis* (↑ 2/ ↓ 0)
├─ Yes, if you have enough RAM, but it will be painfully slow. ⏤ by *Vishnu_One* (↑ 1/ ↓ 0)
├── Absolutely not true. Ram is the only constraint. You need 32 gb to run the 4bit comfortably. It runs at 18 t/s on an M1 Max.   
I don’t even know if a base M1 can have 32 GB of RAM, but is it did, it would run at 6/7 t/s which is still usable ⏤ by *Valuable-Run2129* (↑ 2/ ↓ 0)
├── Yeh gotcha, seems like you need a big ass rig to run it ⏤ by *short_snow* (↑ 1/ ↓ 0)
├─── It completely depends on which actual M1 chipset you have as well as how much RAM. On my M1 ultra I can run this thing at about 20ish tokens per second with 16k context ⏤ by *JacketHistorical2321* (↑ 10/ ↓ 0)
├──── deleted 
└────

##### Does it have 14b version? ⏤ by *FirstReserve4692* (↑ 2/ ↓ 0)
├─ yes ⏤ by *Vishnu_One* (↑ 3/ ↓ 0)
└────

##### Wait what? Does this have a context size of 128K? really? ⏤ by *HeftyCarrot7304* (↑ 2/ ↓ 0)
##### The new 32B is way better than the 7B that i was using BUT it is nowhere near to outperform Claude and maybe it is not the model itself but the internal pipeline that anthropic use to pass user requests to Claude model.

I am testing the Qwen 32B in Q4_K_M to generate tests for a Golang REST API compared to Claude, i fed the same data to both of them but Qwen made a lot of errors while Claude made 0! ⏤ by *Mochilongo* (↑ 2/ ↓ 0)
├─ I tried qwen 2.5 32b q8. pretty good, gpt-4o comparable with my small testset. q4 does not do it justice. ⏤ by *shaman-warrior* (↑ 3/ ↓ 0)
├── Thanks i will give it a try, what do you use as a front end for chat? I have tried Open WebUI and LM Studio. ⏤ by *Mochilongo* (↑ 1/ ↓ 0)
├─── open web ui is very nice ⏤ by *shaman-warrior* (↑ 1/ ↓ 0)
├─ It's prob because you're using q4. For coding related tasks there's a noticeable real world performance difference when you use anything below q8. ⏤ by *z_3454_pfk* (↑ 1/ ↓ 0)
└────

##### That rotating globe demo is stunning. ⏤ by *phenotype001* (↑ 2/ ↓ 0)
##### I have the Qwen2.5-Coder-7B-Instruct-4bit MLX running in LM Studio on a MacBook with M2 Pro.

Tried the first example, and apart from an incorrect URL to the three.js source, everything was OK. Inserted the correct URL, there was the spinning globe.

The second example was a bit more tedious. Wrong URL to three.js again, and also wrong URLs to non-existent pictures. The URLs to the wrong pictures were not only in the TextureLoader calls, but also included in script tags (?!) at the top of the body section, next to the one including the three.js script. Once I fixed all of that in the code, I have a spinnable zoomable globe with bump mapping.

https://preview.redd.it/jmwj02at8i0e1.png?width=726&amp;format=png&amp;auto=webp&amp;s=9934c42271f8cc503fde9e28cfb2cbdb6f8a05a0

Code production only took a couple of seconds for the first one (31.92 t/s, 1.16s to first token), maybe 10 seconds or so for the second example (20.94 t/s, 4.39s to first token).

Just noticed that my MacBook was accidentally running in Low Power mode... ⏤ by *Density5521* (↑ 2/ ↓ 0)
├─ That is impressive! ⏤ by *Vishnu_One* (↑ 1/ ↓ 0)
├── Did Qwen get the URLs right in your attempts? Or did you also have to fix them?

If the smaller version only gets minor details like external URLs wrong, then it's still a decent result one can work with.

It's a shame I only have the 16 GB MacBook, otherwise I could try larger (read: more precise) LLMs. ⏤ by *Density5521* (↑ 1/ ↓ 0)
├─── As you can see from the GIF, this is a single prompt. I haven’t asked a second question. You can test it on q8. ⏤ by *Vishnu_One* (↑ 1/ ↓ 0)
├─ It's prob because you're using q4. For coding related tasks there's a noticeable real world performance difference when you use anything below q8. ⏤ by *z_3454_pfk* (↑ 1/ ↓ 0)
└────

##### I also have a dual 3090 setup, how did you get this working to use both GPUS? ⏤ by *sugarfreecaffeine* (↑ 2/ ↓ 0)
├─ Ollama docker will use all available GPU's , I posted by docker compose here. check my profile. 

    docker run -d --gpus=all -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama ⏤ by *Vishnu_One* (↑ 7/ ↓ 0)
├── deleted 
├─ LM Studio auto uses both cards for me, at least in my CMP rig ⏤ by *gaspoweredcat* (↑ 3/ ↓ 0)
└────

##### can i run it on a single 3090? ⏤ by *hotpotato87* (↑ 2/ ↓ 0)
├─ Yes, it will have a smaller context. ⏤ by *knownboyofno* (↑ 3/ ↓ 0)
├── Oh i c, how much can we expand the context window? Right now im spending like $20usd per week on claude api. ⏤ by *hotpotato87* (↑ 1/ ↓ 0)
├─── deleted 
├── To clarify, from my testing so far, with 24GB VRAM you can fit ~8K context with the 32B model at Q5_K_S quant, and 16K context with the Q4_K_M quant (~32K with 8-bit quantized KV; though quality might suffer.)

This is all with the Windows desktop etc. running. ⏤ by *Nonsensese* (↑ 1/ ↓ 0)
├─ Yes. I'm using a 5.0bpw EXL2 version with 32k context and it fits in about 23GB of VRAM. Can't remember the exact number, 22.6GB or something like that. ⏤ by *GregoryfromtheHood* (↑ 1/ ↓ 0)
└────

##### ```
Generate a WebGL visualization that uses fragment shaders and signed distance fields to render realistic clouds in a canvas element.
``` ⏤ by *LocoMod* (↑ 2/ ↓ 0)
├─ [https://pastebin.com/B1ba48uX](https://pastebin.com/B1ba48uX) ⏤ by *Vishnu_One* (↑ 4/ ↓ 0)
├── Failed. But it did generate a good starting point. With a couple of more steps we might have something. :)

https://preview.redd.it/mida53826e0e1.png?width=544&amp;format=png&amp;auto=webp&amp;s=3b588a2881212ff6730d82d764dfd18667c2d102 ⏤ by *LocoMod* (↑ 7/ ↓ 0)
├─── Adjust the prompt, you will get what you want.   
just tell it to create a snake game vs   
created a complete Snake game with all the requested features. Here are the key features:  
Game Controls:  
Start button to begin the game  
Pause/Resume button to temporarily stop gameplay  
Restart button to reset the game  
Fullscreen button to expand the game  
Arrow keys for snake movement

Visual Features:  
Gradient-colored snake  
Pulsating red food  
Particle animation when food is eaten  
Score display at the bottom  
Game over screen with final score

Game Mechanics:  
Snake grows when eating food  
Game ends on wall collision or self-collision  
Food spawns in random locations  
Score increases by 10 points per food eaten

second prompt created everything we asked. ⏤ by *Vishnu_One* (↑ 4/ ↓ 0)
├──── The snake game is a common test. This is likely in its training data. The idea is to test a challenging prompt that is not common. I have generated a snake game with much less capable models in the past. It does not take a great code model to do this. If you can get a model to generate something uncommon like 3D graphics using webGL then you know its good. ⏤ by *LocoMod* (↑ 10/ ↓ 0)
├───── I generated a fully working snake game 0-shot with Qwen 2.5 0.5B coder, which is kinda insane. Because not only did it follow the instruction well enough, it retained enough of its training data to know snake and make a working game for it. 

Can you imagine traveling back to 2004. Telling people you have an AI that takes 512mb of RAM and runs on some pentium 4 system and can code games for you. It's completely bonkers to think about. ⏤ by *Down_The_Rabbithole* (↑ 3/ ↓ 0)
├───── deleted 
├──── No. Previously, when I simply tested the code capabilities of LLM, I tested them by asking it to generate a tank battle game with more complex requirements. This test is more difficult than creating a snake game. ⏤ by *Front-Relief473* (↑ 1/ ↓ 0)
└────

##### So are you using the Q4KM quant on a dual 3090 setup because you're going for a large context size and can't fit anything better than Q4KM?

It's nice to see it's working so well in your experience even at that quant level! ⏤ by *Calcidiol* (↑ 1/ ↓ 0)
├─ I can run Q8, but I will be testing it soon. For now, Q4 is sufficient. Using Q4 allows me to run two small models. The benefits of using Q8 for larger models are not worth the extra RAM and CPU usage. Large quantization makes sense for 8B or smaller models. ⏤ by *Vishnu_One* (↑ 9/ ↓ 0)
├── Coding is one of the few areas I've encountered where it is worth bumping up the quant as high as you can. ⏤ by *Baader-Meinhof* (↑ 6/ ↓ 0)
├─── Yes for smaller models and no for larger models in my tests. Maybe my questions are simple and not affected by quantization. Example question that I can see a difference in Q4KM and Q8 ? ⏤ by *Vishnu_One* (↑ 7/ ↓ 0)
├──── How many Rs are in the word strawberry \s ⏤ by *LoafyLemon* (↑ 1/ ↓ 0)
├── I run it on one rtx 3090 32b q4km with context 16k getting 37 t/s on llamacpp ⏤ by *Healthy-Nebula-3603* (↑ 7/ ↓ 0)
├─── Impressive ⏤ by *Vishnu_One* (↑ 1/ ↓ 0)
├──── Most impressive ⏤ by *MoffKalast* (↑ 1/ ↓ 0)
├─── Could you share your setup? ⏤ by *sleekstrike* (↑ 1/ ↓ 0)
├──── llama-cli.exe --model Qwen2.5-Coder-32B-Instruct-Q4\_K\_M.gguf --color --threads 30 --keep -1 --n-predict -1 --ctx-size 16384 -ngl 99 --simple-io -e --multiline-input --no-display-prompt --conversation --no-mmap --in-prefix "\\n&lt;|im\_start|&gt;user\\n" --in-suffix "&lt;|im\_end|&gt;\\n&lt;|im\_start|&gt;assistant" -p "&lt;|im\_start|&gt;system\\nYou are a helpful assistant.&lt;|im\_end|&gt;" ⏤ by *Healthy-Nebula-3603* (↑ 2/ ↓ 0)
└────

##### If I had a single 3900, what's the biggest Qwen model I could run, 7B or 14B? Currently I run small models on CPU only, but I'm considering buying a video card to run bigger models. ⏤ by *xristiano* (↑ 1/ ↓ 0)
├─ 14B very easily. Good luck pal. ⏤ by *mahiatlinux* (↑ 4/ ↓ 0)
├─ Use the 32b model, q3\_k\_m is a good sweet spot. ⏤ by *raysar* (↑ 2/ ↓ 0)
└────

##### agreed its incredible, im getting about 10 tokens per sec with the q6kl on a pair of CMP 100-210s ⏤ by *gaspoweredcat* (↑ 1/ ↓ 0)
##### Its crazy the numbers I read in here: 22-37 T/s. I run Q6K with full 130k context and get 7-8 T/s lol ⏤ by *DrVonSinistro* (↑ 1/ ↓ 0)
├─ 130k context is going to be your problem I am guessing ⏤ by *L3Niflheim* (↑ 2/ ↓ 0)
├─ What's the configuration of your computer? ⏤ by *Front-Relief473* (↑ 1/ ↓ 0)
├── 60GB vram (2x P40 + 1x A2000) ⏤ by *DrVonSinistro* (↑ 1/ ↓ 0)
├─ I tested it my 3090 and P40s. My 3090 can do 32tok/sec and 3xP40s got up to 15tok/sec. 

posted the results here: https://www.reddit.com/r/LocalLLaMA/comments/1gp376v/qwen25coder_32b_benchmarks_with_3xp40_and_3090/ ⏤ by *No-Statement-0001* (↑ 1/ ↓ 0)
├── strangely enough, my RTX A2000 slow down my 2x P40s on account that its memory bandwidth is half of the P40s. ⏤ by *DrVonSinistro* (↑ 1/ ↓ 0)
└────

##### I am pretty sure that the following question won't be answered correctly. 😜

  
*Write the Python code to handle the task in Ren'Py of seamlessly transitioning between tracks for an endless background music experience, where the next track is randomly selected from a pool before the current track ends, all while maintaining a smooth cross-fade between new and old tracks. Adopt any insight or strategy that results in the main goal of achieving this seamless transition.*  ⏤ by *IrisColt* (↑ 1/ ↓ 0)
├─ https://pastebin.com/BRt2tNdQ ⏤ by *HeftyCarrot7304* (↑ 1/ ↓ 0)
├── Sadly, module 'renpy.audio.music' has no attribute 'register\_end\_callback'. ⏤ by *IrisColt* (↑ 1/ ↓ 0)
└────

##### It really needs tool use and vision to be totally mind-blowing. ⏤ by *mintybadgerme* (↑ 1/ ↓ 0)
##### Is there a minimal C inference code to drive the weights with? ⏤ by *Historical_Aide_7784* (↑ 1/ ↓ 0)
##### No it is not, I tried it with openrouter on cline and it always get stuck in infinite loop, giving completely random response. ⏤ by *vinam_7* (↑ 1/ ↓ 0)
##### Are you using this with Continue extension on VSCode? Also how much better is it than the 7B model? ⏤ by *NaiRogers* (↑ 1/ ↓ 0)
##### Is it better than O1 mini? ⏤ by *Jumper775-2* (↑ 1/ ↓ 0)
##### Here's a challenge:

Create a k-means clustering algorithm to automatically sort images of cats and dogs (using keras's cats and dogs dataset) into two separate folders, then create a binary classification CNN. ⏤ by *swagonflyyyy* (↑ 1/ ↓ 0)
├─ [https://pastebin.com/Qk6nE44Q](https://pastebin.com/Qk6nE44Q) ⏤ by *Vishnu_One* (↑ 1/ ↓ 0)
├── Interesting. Of course its not an ideal approach what I recommended, but I'm still curious if it can sort a dataset in an unsupervised manner. ⏤ by *swagonflyyyy* (↑ 1/ ↓ 0)
├─── [https://pastebin.com/Br1eah3H](https://pastebin.com/Br1eah3H) ⏤ by *Vishnu_One* (↑ 1/ ↓ 0)
└────

##### May be a dumb question. Do I absolutely need vram to run this model or could I get away with trying to run this on these specs?  
Motherboard: SuperMicro X10SRL-F  
Processor: Intel(R) Xeon(R) CPU E5-2697A v4 @ 2.60GHz  
Memory: 128GB Crucial DDR4  
Raid Controllers: (4) LSI 9211-8i (in alt channels)  
Main Drive: Samsung SSD 990 EVO 2TB NVME (PCIE Adapter)  
Storage: (24) HGST HUH721010AL4200 SAS Drives

Any tips on preferred setup on a bare-metal chassis?

Thanks a ton in advance. ⏤ by *Neilyboy* (↑ 1/ ↓ 0)
├─ It will be VERY SOLO. You need a powerful GPU like 3090 or better. ⏤ by *Vishnu_One* (↑ 1/ ↓ 0)
├── Dang thanks for the reply. Figured if I could finally use the server for something useful lol ⏤ by *Neilyboy* (↑ 1/ ↓ 0)
└────

##### I didn’t know openwebUI has a preview option? That’s openWebUi right? ⏤ by *Whyme-__-* (↑ 1/ ↓ 0)
├─ yes, update to latest version ⏤ by *Vishnu_One* (↑ 1/ ↓ 0)
└────

##### And what is the Op using as interface with artefact-like viz ? Its into VS code ? Something else ? ⏤ by *jppaolim* (↑ 1/ ↓ 0)
├─ OpenWebUI ⏤ by *Vishnu_One* (↑ 2/ ↓ 0)
├── I knew I should give it a try again, last time I was repelled by the initial setup which is so cumbersome vs Lm Studio or Msty which is my favorite now. But definitely this is convenient for the use case… ⏤ by *jppaolim* (↑ 1/ ↓ 0)
├─── Very easy [https://www.reddit.com/r/LocalLLaMA/comments/1fohil2/qwen\_25\_is\_a\_gamechanger/](https://www.reddit.com/r/LocalLLaMA/comments/1fohil2/qwen_25_is_a_gamechanger/) ⏤ by *Vishnu_One* (↑ 1/ ↓ 0)
└────

##### Do two 3090 make inference faster than one? I read that multiple GPUs can boost training but not inference.

And I have another question: what is the best computer to run this model? I'm thinking about building PC with 192GB RAM and NVidia 5090 when it comes out (I have 4090 now which I can already use). Is it worth building this PC or buying M4 Pro Mac Mini with 48/64Gb RAM to run QWEN 2.5 Coder 32B?

And is it possible to use QWEN model to replace Github Copilot in Rider? ⏤ by *mattpagy* (↑ 1/ ↓ 0)
├─ RAM is useless; VRAM is king. I have 32 GB of RAM but allocated 16 GB. If I increase it to 24 GB, the model loads in under 30 seconds; otherwise, it takes about 50 seconds. That’s the only difference—no speed difference in text generation. I’m using two 3090 GPUs and may add more in the future to run larger models. I’ll never use RAM; it’s too slow. ⏤ by *Vishnu_One* (↑ 2/ ↓ 0)
├── So Qwen-2.5-Coder does parallelize itself between two videocards when you load it? ⏤ by *mattpagy* (↑ 1/ ↓ 0)
└────

##### Claude level? That is insane! ⏤ by *Technical_Echidna858* (↑ 1/ ↓ 0)
##### it is very nice to see such developments ⏤ by *SpareFollowing4217* (↑ 1/ ↓ 0)
##### you can run code directly on open webui? I had no idea ⏤ by *KeyObjective8745* (↑ 1/ ↓ 0)
##### If you've got 2x3090 why are you running GGUF? Just curious. I avoid GGUF and always go for EXL2 because I have Nvidia GPUs ⏤ by *GregoryfromtheHood* (↑ 1/ ↓ 0)
├─ there is no exl2 of that model

EDIT: woah they released it, OMG i'm so happy 😎 ⏤ by *infiniteContrast* (↑ 1/ ↓ 0)
└────

##### New to offline llms,  can anyone tell me how I can get this in gpt4all (windows) ⏤ by *skylabby* (↑ 1/ ↓ 0)
##### Can I install this with ollama?  Sorry for being so ignorant. ⏤ by *Jethro_E7* (↑ 1/ ↓ 0)
├─ Yes ⏤ by *Vishnu_One* (↑ 2/ ↓ 0)
└────

##### Anyone got this running on an Apple M4 Pro yet? Considering a new Mac Mini just to run this model! ⏤ by *User-231465* (↑ -3/ ↓ 0)
├─ The 4 bit runs at 22 t/s. On an M1 Max it runs at 17 t/s (both MLX). A Mac Mini will probably run it at 10 t/s due to lower bandwidth ⏤ by *Valuable-Run2129* (↑ 3/ ↓ 0)
├── - ⏤ by *DangKilla* (↑ 1/ ↓ 0)
├─── The mac mini tops at 64 gb ⏤ by *Valuable-Run2129* (↑ 1/ ↓ 0)
├──── - ⏤ by *DangKilla* (↑ 1/ ↓ 0)
└────

##### deleted 
