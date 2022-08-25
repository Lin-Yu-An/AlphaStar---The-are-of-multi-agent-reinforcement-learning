# AlphaStar - The art of multi agent reinforcement learning
  -A look into how the AlphaStar works, and how it was trained to beat the best player in Starcraft II. 
  -And furthermore, to open lots of new possibilities through this way of reinforcement learning.

![](https://rtsgaming.com/wp-content/uploads/2019/07/Starcraft-2-Deep-Mind-AI-Online-AlphaStar.png)

## Overview
  - Description of the topic 
  - Design/implementation 
  - Result 
  - Conclusion/Future work 
  - References

## Description of the topic 
  -Many real-world applications require artificial agents to compete and coordinate with other agents in complex environments. As a stepping stone to this goal, the domain of StarCraft has emerged as an important challenge for artificial intelligence research, owing to its iconic and enduring status among the most difficult professional esports and its relevance to the real world in terms of its raw complexity and multi-agent challenges. 
  -Over the course of a decade and numerous competitions, the strongest agents have simplified important aspects of the game, utilized superhuman capabilities, or employed hand-crafted sub-systems. Despite these advantages, no previous agent has come close to matching the overall skill of top StarCraft players. 
  -I chose to address the challenge of StarCraft using general purpose learning methods that are in principle applicable to other complex domains: a multi-agent reinforcement learning algorithm that uses data from both human and agent games within a diverse league of continually adapting strategies and counter-strategies, each represented by deep neural networks. 
  -AlphaStar was rated at Grandmaster level for all three StarCraft races and above 99.8% of officially ranked human players.

## Design/implementation

###### Why Starcraft II? 
  DeepMind is the creator of AlphaStar, and its purpose is to build an Artificial Intelligence to benchmark how the algorithm (or so called Agent) perform on a wide variety of task.
  ex: Atari, Go, Starcraft II
  But compare to the former 2, DeepMind chose Starcraft II for a few reasons:
1. Imperfect information: On Atari and Go, you can observe the whole board anytime, it's literally the interface of what you see when playing. But on Startcraft, you couldn't, in fact you even need to speculate or even predict what the enemy is doing, and those add further more depth into decision-making.
2. Action space and moves per game: Atari has an action space of 17 and hundreds of moves per game. Go has 361 action space and also hundreds of moves per game. Meanwhile Starcraft has aproximately 10 to the 26 times of action spaces and over thousands of moves per game. Comparatively it's a much more broader game which contains all kinds of possibilities to have anything happen.
3. It's a Real-Time strategy game, which means decision needs to be made in a blink of a second, APM matters on how fast you can progress in game, and make very precies moves by any given second.

###### Set rules for the AI side
![](https://assets-global.website-files.com/621e749a546b7592125f38ed/62271f5159c05b00cb86acbb_AlphaStar%2009.jpg)
  AlphaStar's APM (Action Per Minute) is purposely lower, so it doens't go inhuman speed that normal human cannot achieve, this is to be fair on the base. What matters are the decision making and execution, not just pure speed.

  From going through possible decisions through neuronetwork until the decision was made, it takes AlphaStar about 350 miliseconds as a reaction, it's actually higher than human which are around 200-250 miliseconds usually.

###### How it is trained?
![](https://assets-global.website-files.com/621e749a546b7592125f38ed/62271e2f604e640534eeca99_AlphaStar%2003.gif)
  As for the "form" of Alphastar, it's actually just a GPU, that takes its time to compute and execute.
  In terms of the actual training, it uses what's called a Tensor Processing Units (an AI accelerator application-specific integrated circuit developed by Google for neural network machine learning) which live in the Google Cloud, and the agents in the AlphaStar League actually uses 16 Tensor Processing Units. (In more plain words, it's kind of like 50 GPUs). Here introducing AlphaStar League.

###### AlphaStar League 
![](https://tweakers.net/nieuws/148360/professionele-starcraft-ii-speler-verliest-toernooi-van-deepminds-ai-alphastar.html)
  This is the training ground for all of the agents. According to the photo above: the first competitor of the league is actually the neural network that is trained from human data, and as each subsequent iteration, new agents are forked and branched from that previous agent and added to the AlphaStar League. These agents then play matches against each other competitors in the league. 
  Depending on what happens in the those matches, their neural networks are updated by a process called "Reinforcement Learning". So that is where it learn all kind of strategies and how to effectively play against it. 
  In addition, those competitors are encouraged to specialize by adapting their personal learning objectives. For example: some of them might have preferences to play against particular opponents or build a specific types during the game.
  At the end of the AlphaStar League, Deepmind selects the least exploitable set of five agents out of the league, and those are the five different agents that went against the pros during the demonstation video. (links below)
  What's even more crazier is the whole league can be run in multiple times in a go and fasten the whole speed of processing. By the time of the showcase in the demonstation video, AlphaStar has an accumulated 200 years of experiences of playing solely Starcraft II.
  
## Result 
![](https://user-images.githubusercontent.com/96692658/186757826-79b053ee-5c7b-49ba-a70a-6a97d13bb951.PNG)
  The results were surprised by both sides, the developers can't believe that AlphaStar actually defeated 2 pros (TLO and MaNa) with no lost, and the pros that can't believe how strong AlphaStar was. Overall, by watching the gameplay for every single matches, AlphaStar always had a bit lower APM and some strange decisions here and there. But in the broader picture regarding the whole game, both players could not find a way to win over it even one game.
  AlphaStar was rated at Grandmaster level for all three StarCraft races and above 99.8% of officially ranked human players.
  It was a huge success for the team in Deepmind.

## Conclusion/Future work 
![](https://user-images.githubusercontent.com/96692658/186760534-b9fbd1f9-f0a4-4e9c-9f38-66c50ae7d4bb.jpg)
  As the comment from one of the developer in Deepmind said: AlphaStar's end goal is not to just be playing video games and beats human race. It could have all kinds of possibility of where it can be implemented. Weather prediction and climate modeling, or even in this topic's case: to help learning more and new strategies regarding on Starcraft II competitive scene for the pros or people in the future who might be interested.

## References
  Research paper article : https://www.nature.com/articles/s41586-019-1724-z.epdf?author_access_token=lZH3nqPYtWJXfDA10W0CNNRgN0jAjWel9jnR3ZoTv0PSZcPzJFGNAZhOlk4deBCKzKm70KfinloafEF1bCCXL6IIHHgKaDkaTkBcTEv7aT-wqDoG1VeO9-wO3GEoAMF9bAOt7mJ0RWQnRVMbyfgH9A%3D%3D
  
  Deepmind blog website : https://www.deepmind.com/blog/alphastar-mastering-the-real-time-strategy-game-starcraft-ii
  
  AlphaStar v.s. Starcraft pros demonstration : https://www.youtube.com/watch?v=cUTMhmVh1qs
  
  Final results for AlphaStar agent : https://www.youtube.com/watch?v=xP7LwZxq0ss&t=50s
