# Sharing machine learning models

Up to now, we have been focus on sharing code and collaborating with others on GitHub.
But what about sharing machine learning models?

For ML models, we can use the same principles of version control and collaboration that 
we have seen before. However, there are some additional considerations when sharing models, 
such as the size of the model, the data, and the dependencies. GitHub has some limitations 
when it comes to sharing large files, so we may want to use other tools and platforms to share
large machine learning models.

For this kind of content, we can use the same tools that we have seen before, like GitHub, 
but we can also use other platforms like [Hugging Face](https://huggingface.co/),
[Weights & Biases](https://wandb.ai/), and [TensorFlow Hub](https://tfhub.dev/).

In this section, we will see how to share machine learning models using Hugging Face.


## Hugging Face

```{figure} ../figures/hf-logo.png
:width: 200px
:align: center
```

Hugging Face's platform and libraries, particularly the `Transformers` library and 
`Hugging Face Hub`, enable efficient and collaborative code sharing. 
By providing access to a vast array of models, datasets, and tools, 
Hugging Face empowers developers, researchers, and organizations to accelerate 
their projects.

We can use Hugging Face to share models, datasets, and training scripts.

### Sharing models using the web interface

To share a model on Hugging Face, you need to create a repository on the platform.
You can do this by following these steps:

1. Go to the [Hugging Face website](https://huggingface.co/)
2. Sign in or create an account
3. Click on the `New Model` button on the top right corner
4. Fill in the details of the model, such as the name, description, and tags

![New Model](../animation/new-model.gif)

### Sharing models using the ModelHubMixin class

Perhaps, a better way to share models is by using the `ModelHubMixin` class from the `transformers` library.
This functionality allows you to upload your model to the Hugging Face Hub directly from your Python code.

huggingFace offers a range of mixins for different frameworks, such as PyTorch, Keras, and Fastai.

Here is an example of how to use the `PyTorchModelHubMixin` class to upload a model to the Hugging Face Hub
using a PyTorch model:

1. Install the `transformers` library

```bash
pip install transformers
```

2. Create a PyTorch model

Define and train your PyTorch model as usual. Ensure your model class inherits from 
`torch.nn.Module`.

3. Implement PyTorchModelHubMixin

Make your model class inherit from `PyTorchModelHubMixin`. 
This mixin provides methods to save and load models from the Hugging Face Hub.

```Python
from transformers import PyTorchModelHubMixin
import torch.nn as nn

class MyModel(nn.Module, PyTorchModelHubMixin):
    def __init__(self):
        super(MyModel, self).__init__()
        self.layer = nn.Linear(10, 10)

    def forward(self, x):
        return self.layer(x)

# Instantiate and train your model as usual
model = MyModel()
# ... train your model

```

4. Save the model to the Hugging Face Hub

Use the save_pretrained method to save your model to a local directory.

```Python
model.save_pretrained("./my_model")
model.push_to_hub(
    "my_model",
    token=<your_token>,
)
```

5. Load the model from the Hugging Face Hub

Use the from_pretrained method to load your model from the Hugging Face Hub.

```Python
model = MyModel.from_pretrained("my_model")
```

## GitHub and HuggingFace

GitHub and Hugging Face can be used together to share machine learning models.
You can use GitHub to store the code and the training scripts, and Hugging Face to store the models.
This way, you can have a complete pipeline for sharing machine learning models.
Also, in this way, you can use the version control features of GitHub to track changes in the code and the models.

In a similar way, you could share public dataset in Hugging Face `Datasets` and use it 
in your GitHub repository.



