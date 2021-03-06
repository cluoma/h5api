HALO API R Package
====================

Provides easy access to the Halo 5 and Halo Wars 2 web APIs provided by 343i.

A developer API key is required to use this package. You can get one from [here](https://developer.haloapi.com/)

Package documentation is rather sparse so I recommend using Microsoft's official [API documentation](https://developer.haloapi.com/docs/services/).

**Installation:**
<pre>
install.packages(c("devtools","httr","jsonlite"))
library(devtools)
install_github("cluoma/haloR")
</pre>

**Example:**
<pre>
library(dplyr)
library(haloR)

key <- "XXXXXXXXXXXXXXXXXXXXX"
player <- "CLWakaLaka"

profile <- h5_ServiceRecord(mode = "arena", player, key = key)

print(paste0(
  player, " has an overal K/D ratio of ",
  round(profile$Results$Result$ArenaStats$TotalKills /
          profile$Results$Result$ArenaStats$TotalDeaths,
        digits=2)
))
</pre>
