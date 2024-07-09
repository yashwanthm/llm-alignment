
# Tune and align LLMs with your data to deliver inferencing

**Table of contents**
 1. [Setup your environment](#setup-your-environment)
 2. [Prepare your data](#prepare-your-data)
 3. [Train Model, Test the Model](#)
 4. [Serve the model locally with Podman Desktop AI Lab Extension](#serve-the-model-locally-with-podman-desktop-ai-lab-extension)
 5. [Integrate the model into you app](#)
 6. [Deploy the model](#)
 7. [Switch endpoint](#)
 8. [Deploy Model- <PENDING>](#)
 9. [Deploy Application - <PENDING>](#)

## Setup your environment

 1. `mkdir instructlab`
 2. `cd instructlab`
 3. `source venv/bin/activate` - Run this first to activate your virtual environment. This will be required each time you create a new instance of the terminal
 4. Configure your InstructLab environment by running `ilab config init`. This will generate a `config.yaml` on your directory
 5. Start the model server `ilab serve`, keep it running so that you can chat with the model
 6. Chat with the model on a different terminal using `ilab chat`. This will initiate a chat session on the CLI

### Using Granite model 
 1. `ilab download --repository instructlab/granite-7b-lab-GGUF --filename=granite-7b-lab-Q4_K_M.gguf` 
 2. `ilab serve --model-path models/granite-7b-lab-Q4_K_M.gguf` 
 3. `ilab model chat --model
    models/granite-7b-lab-Q4_K_M.gguf`
    
#####  Use Granite as the default model
`nano config.yaml`
Change the model_path on `config.yaml`  to `model_path: models/granite-7b-lab-Q4_K_M.gguf`

## Prepare your data <a name="preparedata"></a>
[Taxonomy](https://github.com/instructlab/taxonomy) enables developers and data scientist to create a version of the knowledge that your model will be trained on. Developers can use `git` to manage to add a source control to the taxonomy that will help you control the data your model uses to respond back to the prompts. 

1. Create `qna.yaml`, use https://github.com/yashwanthm/training-tests/blob/main/story/qna.yaml for a reference
2. copy the qna.yaml to taxonomy/knowledge `cp ~/my_knowledge/story/qna.yml taxonomy/knowledge/literature/novels/SkyboundMysteries`
3. Check if the taxonomy is valid using `ilab diff`
4. Generate some synthetic data based on the qna.yaml that will be used to train the data using `ilab generate`
5. Review generated data at --path--

## Train the model
1. Train the model using `ilab train`
2. Serve the newly generated model using `ilab serve --model-path instructlab-merlinite-7b-lab-trained/instructlab-merlinite-7b-lab-Q4_K_M.gguf`
3. Chat with the newly generated model on a new terminal using `ilab model chat -m instructlab-merlinite-7b-lab-trained instructlab-merlinite-7b-lab-Q4_K_M.gguf`


## Serve the model locally with Podman Desktop AI Lab Extension
1. import - add screenshots
2. deploy - add screenshots
3. Copy the api call

## Add inference to your app
1. Add the API call to your app
2. Display the response
