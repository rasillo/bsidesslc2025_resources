# LLM-Assisted Risk Management for Small Teams and Small Budgets
## Intro blurb
What: My talk will help small, underfunded teams identify relevant risk management opportunities and iteratively improve defenses in small, manageable ways, by using LLM's to parse through complex risk management and IT architecture security documents from NIST and Microsoft.

Results: My talk will provide this information in order to help attendees create a contextually-aware, generatively assisted action plan for improvements to an organization's cybersecurity stance that can run on basic machinery, with minimal prior skills.

Why? If you gain a better understanding of your organization's risk status, you are better equipped to defend against lone wolf hackers, motivated teams, hacktivists, and Advanced Persistent Threats.

## Files inside this repo
I'm including several copies of files in their original PDF format, and then their cleaned and converted Markdown format. I'm also including the basic commands you need to set up the Ollama and Open WebUI, along with links to their original doc sites.

These files were converted using [Docling](https://https://github.com/docling-project/docling), a Python package that can scan through PDF files (using easyOCR and other widgets).

## Open WebUI links and commands
[Open WebUI Docs](https://docs.openwebui.com/getting-started/quick-start/)

`docker pull ghcr.io/open-webui/open-webui:main`

`docker run -d -p 3000:8080 -v open-webui:/app/backend/data --name open-webui ghcr.io/open-webui/open-webui:main`

This will get you a basic container set up, which **will not** have volume storage mounted.

Follow the original Open WebUI docs page linked above to get persistent storage agnostic of the container instance's lifecycle.

## Ollama links and commands
[Ollama Docker links](https://ollama.com/blog/ollama-is-now-available-as-an-official-docker-image)

For **Linux**, see excerpt from the post.

> To get started using the Docker image, please use the commands below.

> ### CPU only
> `docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama`

> ### Nvidia GPU
> Install the [Nvidia container toolkit.](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html#installation)

> Run Ollama inside a Docker container

> `docker run -d --gpus=all -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama`

> Run a model

> Now you can run a model like Llama 2 inside the container.

> `docker exec -it ollama ollama run llama3.2`

**MacOS and Windows download link:** [Ollama Download Link](https://ollama.com/download)

**MacOS Note**: Ollama needs to be installed directly, on Macs, if you're using Docker Desktop. Docker Desktop on Mac doesn't support GPU acceleration. I can't verify whether K3s or other K8s spins can do so, I have not tested it.

## Connecting Open WebUI and Ollama together
If you follow the basic Docker commands above, you should have Open WebUI's container running on port `3000`, and Ollama should be running on port `11434`.

Follow this excerpt from the Open WebUI docs to set up the Ollama instance as one of the model providers.

> ### Step 1: Setting Up the Ollama Connection

> Once Open WebUI is installed and running, it will automatically attempt to connect to your Ollama instance. If everything goes smoothly, you’ll be ready to manage and use models right away.

> However, if you encounter connection issues, the most common cause is a network misconfiguration. You can refer to our connection troubleshooting guide for help resolving these problems.

> ### Step 2: Managing Your Ollama Instance

> To manage your Ollama instance in Open WebUI, follow these steps:

> Go to Admin Settings in Open WebUI.

> Navigate to Connections > Ollama > Manage (click the wrench icon).

> From here, you can download models, configure settings, and manage your connection to Ollama.

## Conclusion

That's it! You're now capable of doing the same thing this talk did. Now start pulling down files, RAGing them, and getting wise on your organization's risk management stature.