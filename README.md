code to be downloaded and run directly in NetLogo
set up the following in the interface to ensure the code works as intended
graphs to study the results can be set-up according to personal preference and requirements

buttons - "go" and "setup" (turn on the option for forever in the go button)
sliders - "initial-number-of-agents" and "risk-threshold"
switch - "communal-interaction?" 

Initial Model environment
The Model is set up in a 33x33 grid of patches. At the start of each trial, N agents are randomly distributed across the grid, each agent is assigned a strategy of either Cooperation(blue) or Defection(red), each agent is initialized with a starting wealth of 50 units. 

Interaction systems
2.2.1 Risk Threshold
The risk threshold is central to this model, if the wealth of an agent drops below the ‘Risk Threshold’ then the agent switches to a ‘refuser’ strategy in which the agent gains 0.5 wealth points irregardless of the agent its interacting with, This has key implications in differentiating the two versions of the model being discussed

Interaction choice
This is the logic in the code that allows for either single interactions where the player chosen is randomized, or for the agent to interact with all of its neighbours, an if-else statement supplemented by a switch in the interface allows for this.

Cost of Living
The cost of living is a piece of logic implemented that depletes one wealth point per tick to add a sense of danger to disincentivise refusal, this also differentiates the two versions of the game being played as one acts as a guaranteed sink where as the other brings back swift recovery.

Reproduction and Death
When the agents reach wealth > 100, they can reproduce, although reproduction is only allowed once every 20 ticks to prevent computational issues and also to more accurately simulate real world conditions. Upon reproduction, the parent loses 50 wealth points which are given to the offspring.The offspring has the same strategy as the parent. The offspring is spawned as close as possible to the parent unless the map is 100% full, then the offspring will fail to be spawned. There is a 5% chance that the offspring flips its strategy i.e. a cooperator becomes a defector and vice versa. If an agent reaches 0 wealth points, then it shall Die and be removed from the game.
