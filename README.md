# LLM-Assisted Risk Management for Small Teams and Small Budgets
## Intro blurb
What: My talk will help small, underfunded teams identify relevant risk management opportunities and iteratively improve defenses in small, manageable ways, by using LLM's to parse through complex risk management and IT architecture security documents from NIST and Microsoft.

Results: My talk will provide this information in order to help attendees create a contextually-aware, generatively assisted action plan for improvements to an organization's cybersecurity stance that can run on basic machinery, with minimal prior skills.

Why? If you gain a better understanding of your organization's risk status, you are better equipped to defend against lone wolf hackers, motivated teams, hacktivists, and Advanced Persistent Threats.

## Files inside this repo
I'm including several copies of files in their original PDF format, and then their cleaned and converted Markdown format. I'm also including the basic commands you need to set up the Ollama and Open WebUI, along with links to their original doc sites.

These files were converted using [Docling](https://https://github.com/docling-project/docling), a Python package that can scan through PDF files (using easyOCR and other widgets).

### Open WebUI links and commands
[Open WebUI Docs](https://docs.openwebui.com/getting-started/quick-start/)

`docker pull ghcr.io/open-webui/open-webui:main`

`docker run -d -p 3000:8080 -v open-webui:/app/backend/data --name open-webui ghcr.io/open-webui/open-webui:main`

This will get you a basic container set up, which **will not** have volume storage mounted.

Follow the original Open WebUI docs page linked above to get persistent storage agnostic of the container instance's lifecycle.

### Ollama links and commands
[Ollama Docker links](https://ollama.com/blog/ollama-is-now-available-as-an-official-docker-image)

For **Linux**, see excerpt from the post.

> To get started using the Docker image, please use the commands below.

> #### CPU only
> `docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama` 

> #### Nvidia GPU
> `Install the Nvidia container toolkit.`
> `Run Ollama inside a Docker container`
> `docker run -d --gpus=all -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama`

**MacOS Note:** [Ollama Download Link](https://ollama.com/download)

Ollama needs to be installed directly, on Macs, if you're using Docker Desktop. Docker Desktop on Mac doesn't support GPU acceleration. I can't verify whether K3s or other K8s spins can do so, I have not tested it.

**Windows Note:** Docker Desktop for *Windows* has some fairly specific restrictions. It's a bit of a pain. I suggest you run Ollama as a system service through a WSL2 instance in that case. [Ollama Windows download](https://ollama.com/download/windows)