# Azure Machine learning pipeline and component overview



## What is Azure Machine Learning pipeline? 

An Azure Machine Learning pipeline is an independently executable workflow of a complete machine learning task. Azure Machine Learning pipelines help you build, optimize, and manage machine learning workflows with following benefits:

- Simplicity
- Speed
- Repeatability
- Flexibility
- Versioning and tracking
- Modularity
- Quality assurance
- Cost control

These benefits become significant as soon as your machine learning project moves beyond pure exploration and into iteration. Even simple one-step pipelines can be valuable. Machine learning projects are often in a complex state, and it can be a relief to make the precise accomplishment of a single workflow a trivial process.



## What is Azure Machine Learning component? 
A component is self-contained set of code that performs one step in the ML workflow (pipeline), such as data preprocessing, model training, model scoring and so on. A component is analogous to a function, in that it has a name, parameters, expects certain input and returns some value. 
 
Data scientists or developers can wrap their arbitrary code as Azure Machine Learning component by following the component specification .

### Component specification

A component specification in YAML format describes the component in the Azure Machine Learning system. A component definition has the following parts:

- **Metadata:** name, description, etc.
- **Interface:**: input/output specifications (name, type, description, default value, etc).
- **Implementation:**: A specification of how to run the component given a set of argument values for the component’s inputs, including source code and environment required to run the component. 

Refer to [component spec definition](https://github.com/Azure/DesignerPrivatePreviewFeatures/blob/master/azureml-modules/docs/module-spec-definition.md) for more details. 

### What's the benefit of component? 

Currently Azure Machine Learning offers PipelineStep as the basic building block of machine learning pipeline. PipelineStep is one-off wrap of code that cannot be reused across different pipelines. Compare to PipelineStep, component greatly simplifies the ML pipeline develpoment lifecycle, enables reproducibility and accelerates the collaboration for all-skill data scientists in a team:
 
- **Composability:** This is the native benefit of component. It hides the complicated logic, and only exposes simple interface. So component consumers don't need to worry about underlying implementation. They can easily use components built by themselves or by others. In the meanwhile the ground truth (component specification) of a component is visible, making secondary development easy. 
- **Reusability:** Component can be easily reused across different ML pipelines, different ML workspaces, even different organizations.
- **Easy development, testing & debug:** Rich SDK and CLI features to make component development, testing and debug much easier. See [component development overview](./component-development-overview.md) to learn more.
- **Easy pipeline authoring:** Once a component is registered in the workspace, it can be easily consumed in both Python Python SDK and drag-and-drop Designer UI.
- **Reproducibility:** By capturing all information in component specification, AML Component can be easily reproduced in different environments. Components can be managed in versions so it's easy to trace back if a data scientist wants to reproduce a specific experiment result.
- **Sharing & collaboration:** Data scientists who prefer low-code/no-code can use Designer UI to quickly prototype and export the pipeline to Python code for code-first data scientists for further tuning or check in. The exported Python notebook can also be submitted to different workspaces for sharing & collaboration.

[video-show-component-value-prop]() (to-do)

## Next steps

### Consume existing components 

[Component gallery](https://github.com/tichx/azureml-pipeline-components-gallery) is an open community for data scientists to contribute, share, and find machine learning pipelines as well as custom-built components to be used in Azure Machine Learning. It has more that 50 components for common machine learning tasks. Source code of all components can be found in the gallery. 

Follow [this toturial](./tutorial-use-existing-component-to-build-pipeline.ipynb) (to-do) to learn how to consume a component from the gallery. 


### Build your custom component


- Read the [component development overview](./component-development-overview.md)
- Follow the [tutorial to create your first component](tutorial-create-first-component.ipynb)  
