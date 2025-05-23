
# Step 7: Local Inference with Foundry Local (10 min)

**Notebook:** `07.Local_inference_AIFoundry.ipynb`

**Purpose:** Deploy and test your optimized, distilled model on your local machine using Azure Foundry Local. This step demonstrates how to serve and interact with your model in a production-like, resource-constrained environment. You will be running this notebook from the Skillable VM. Please open the folder `C:\Users\LabUser\Desktop\lab\Build25-LAB329\Lab329\Notebook` which is located on the desktop of your VM called `lab`.

We have also provided a downloaded version of the model in `C:\Users\LabUser\Desktop\lab\fine-tuning-phi-4-mini-onnx-int4-cpu`, accessible via the `lab` folder on the desktop.

This notebook guides you through running local inference with your optimized model using Azure Foundry Local. After downloading and preparing your model in previous steps, you will use Foundry Local to serve and interact with your model on your own machine.

## What You'll Learn
- How to install and configure Azure Foundry Local
- How to prepare your model and configuration for local serving
- How to launch a local model server using Foundry
- How to interact with your model using the Foundry CLI and Python SDK
- How to send prompts and receive completions from your model


#### Instructions

1. **Launch the Foundry Local Model Server**
   - Open a terminal in your model directory.
   - Start the server:

     ```
     foundry model run ./inference_model.json
     ```

   - The server will load your model and provide a local endpoint for inference.

2. **Test Inference via CLI or Python SDK**
   - **CLI:** Use the interactive chat or send prompts directly in the terminal.
   - **Python SDK:** Install the Foundry Python SDK and run:
     
     ```
     from foundry import FoundryClient
     client = FoundryClient(local_url="http://localhost:8080")
     response = client.chat("What is the capital of France? A) Berlin B) London C) Paris D) Madrid E) Rome")
     print(response)
     ```
   - Try your own multiple-choice questions or prompts.

3. **Useful Foundry CLI Commands**
   - `foundry model list` — List available models
   - `foundry --help` — See all commands and options

4. **Next Steps**
   - Explore prompt engineering, benchmark performance, or integrate the local server into your apps.
   - See the [Foundry Local documentation](https://github.com/microsoft/Foundry-Local/tree/main/docs) for advanced usage.

---

## Next Steps
- Experiment with prompt engineering and system instructions
- Benchmark your model's performance locally
- Integrate the local Foundry server into your own applications
- For more details, see the [Azure Foundry Local documentation](https://github.com/microsoft/Foundry-Local/tree/main/docs)

---

**Congratulations!** You have now deployed and tested your compact model in a real-world, local environment using Azure Foundry Local.