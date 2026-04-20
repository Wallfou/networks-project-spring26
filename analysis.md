# Analysis

The analysis was done from Bloomfield, CT (41.83°N, 72.73°W) instead of Boston, since the ISP says my public IP address lives there. Distances and inefficiency ratios below use that IP-reported point as the origin.

## 1. Highest inefficiency

The highest inefficiency ratios were observed for Sendai and Johannesburg, which was around 17.1 in each case, with Sendai marginally higher. This outcome doesn't mean a lack of connectivity to Japan. Public cable maps show extensive trans-Pacific and intra-regional capacity serving Japan. The elevated ratio for Sendai is more because of the application-layer and origin-host behavior for `http://www.tohoku.ac.jp`, including HTTP redirection, server response time, and the absence of a globally distributed edge cache comparable to the Google targets.

## 2. Closest to the theoretical minimum

The lowest inefficiency ratio was recorded for Mumbai (about 1.32), followed closely by Sydney and Singapore. For large services like Google, the same hostname is usually answered from many data centers around the world. The traffic is steered toward one that is geographically close to my location, not necessarily to the city in the domain name. That keeps measured delay low, even though the label on the chart is only a rough geographic tag, not proof that every packet traveled to that exact city.

## 3. Lagos and Europe

Despite the long distance to Lagos, Google Nigeria’s median RTT (~192 ms) was similar to Google in London and Frankfurt. That pattern fits how international routing works wth networks serving users in Africa frequently reach the wider Internet through interconnection in Europe, where many carriers and content providers already exchange traffic. A request to a Nigerian domain may therefore follow a path that touches Europe, or be satisfied from Google infrastructure that is not physically in Lagos. Over the longer term, more direct submarine cables to Africa, stronger Internet exchange points on the continent, and more locally hosted content and caches would shorten paths for users and reduce reliance on detours.
