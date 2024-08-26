---
draft: false
title: "How to create 20,000 lineups in less than 3-minutes"
snippet: "Ornare cum cursus laoreet sagittis nunc fusce posuere per euismod dis vehicula a, semper fames lacus maecenas dictumst pulvinar neque enim non potenti. Torquent hac sociosqu eleifend potenti."
image: {
    src: "https://images.unsplash.com/photo-1593720213428-28a5b9e94613?&fit=crop&w=430&h=240",
    alt: "Generate 20k lineups in less than 3 minutes"
}
publishDate: "2024-08-22 10:35"
category: "Tutorials"
author: "numeric"
tags: [lineup construction, python, optimization, draftkings]
---

## <b> Imagine cranking out 150 lineups in seconds—feels pretty good, right? Now, picture scaling that up to 20,000 in under 3 minutes. Yeah, it's real, and this breakthrough is about to change everything for DFS managers.</b>

I used to run Python scripts to generate between 500 and 2,000 lineups in under 10 minutes max. Then, I'd use that set to run a Monte Carlo simulation, modeling the contest I planned to enter. From there, I used machine learning to create a model that picked the lineups with the best chance of winning.

After taking a break from daily fantasy, my dev skills have grown tremendously. About a month ago, I had a revelation: instead of generating thousands of lineups at once, I could run my daily fantasy sports engine to generate a smaller batch—say, 100 lineups—and then use a bash script to run the engine multiple times in parallel. Since 100 lineups take less than 5 seconds, I can scale up as much as I want by running as many parallel iterations as needed.

To generate 20,000 lineups, I run opt_nfl multiple times using a bash script called dfs_nfl.sh. This approach is faster than running opt_nfl once for 2,000 lineups. The output of the bash scripts is a series of CSV files, each containing a batch of lineups. To sort through duplicates and identify the unique lineups, I run checkLU.py, which filters out the duplicates from the CSV files.

## Step-by-Step Guide to Generate 20,000 lineups

- Run bash dfs_nfl.sh
<Image src="https://lime-prior-stork-152.mypinata.cloud/ipfs/Qma3EVN7kyZDo7EArM8GEjKGQyFcComrL4ZqhcvkqeAcoJ" alt="A bird." width="500" height="500" />

- dfs_nfl.sh calls out opt_nfl.py multiple times
<Image src="https://lime-prior-stork-152.mypinata.cloud/ipfs/QmPYcRDDS5svQHiDz52NEMa8PjoVgCC7wjBQyVZcxyJ6gg" alt="A bird." width="500" height="500" />


- opt_nfl.py uses the py-dfs-lineup-optimizer package and is set to generate 200 lineups.
<Image src="https://lime-prior-stork-152.mypinata.cloud/ipfs/QmS2cfFK86MQnTLLjM56t9hrRrujsZoGgU4Ar3wC6Nkbvo" alt="A bird." width="900" height="1200" />


- Once the optimizer is finished a list of CSVs with duplicate lineups are stored
<Image src="https://lime-prior-stork-152.mypinata.cloud/ipfs/QmQaRE6Gxki2bh8BDMFiEftjAUXPNRi7mgby9evXuybVUP" alt="A bird." width="350" height="350" />



- To find all unique lineups run python checkLU.py.
<Image src="https://lime-prior-stork-152.mypinata.cloud/ipfs/QmRRgwztnNet1psU4RaGmdvSvZWGERNbHmcvXquogv5qB4" alt="A bird." width="900" height="900" />


- checkLU.py will generate a CSV with the unique lineups
  <Image src="https://lime-prior-stork-152.mypinata.cloud/ipfs/QmcDtDuourQDMhAEXaErsf42hh4ss6crELm2UaPcs1p6tc" alt="A bird." width="500" height="500" />



## Path forward: explore ways to find the best lineup 

If your projections and exposures are accurate, you'll have a winning lineup in your set. My next step is to implement a script that selects the top 20 lineups with the best chance of winning. If you found this useful hit the Tip button at the top and add to my coffee fund ☕️

