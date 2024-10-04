## Blockchain Safeguard Project

### Background

Safeguard is an open source project by Arda (at my old job) which can be used to provide transaction insights for your on chain activity in real time and help you safeguard against loosing out on the assets. (Attaching a short snippet of chrome extension interacting with it)

I major work here was to optimise and speed up the API response times by 30-40% (~7-8s to ~2-3s)

Lastly, I worked to get Safeguard open source by setting up code, repo, processes, tags and documentation

Some key practices followed:
- Production grade high quality code
- Clean, documented, well tested code
- Code formatting, utilities like (eslint, prettier)
- Pull Review automated code checks (Github workflows)
- API Documentation with swagger

Github Repo: https://github.com/heethjain21/olynthus

### Tech Stack

- Node.js
- Express
- web3.js
- ethers.js
- Typescript
- Swagger
- Eslint
- Clickhouse
- AWS