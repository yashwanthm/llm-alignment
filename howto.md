- `cd instructlab`
- `source venv/bin/activate`
- Try chatting with the LLM using `ilab serve`, `ilab chat`
- Create qna.yaml
- copy the qna.yaml to taxonomy/knowledge
    ```cp ~/my_knowledge/story/qna.yml taxonomy/knowledge/literature/novels/SkyboundMysteries```
- Check if the taxonomy is valid using `ilab diff`
- Generate some synthetic data based on your data to train the model `time ilab generate`
