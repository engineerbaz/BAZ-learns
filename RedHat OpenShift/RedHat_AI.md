# Red Hat Enterprise Linux AI (RHEL AI)

*RHEL AI serves as a foundation model platform, seamlessly facilitating the development, testing, training, and inferencing of generative AI (GenAI) models for enterprise applications.*

- The Granite family of open source Apache 2.0-licensed LLMs with complete transparency on training datasets.
- A bootable image of RHEL includes popular AI libraries such as PyTorch and hardware optimized inference for NVIDIA, Intel, and AMD.

Red Hat AI platforms
- RedHat Enterprise Linux AI
  - Foundation model platform for developing, testing and running Granite family LLMs
    - provides generative AI 
    - accessable AI to eveyone.
    - ability to do training & inference  
- RedHat OpenShift AI 
  - Integrated MLOPs platform for model LifeCycle Management at scale anywhere
    - provide support for generative & predictive AI with BOYM approach
    - includes compute, collaborative workflows, model serving & monitoring 
    - offer MLOPs capability and scale across hybrid-cloud
    - includes RHEL AI with LLM

<img width="1202" height="617" alt="image" src="https://github.com/user-attachments/assets/47c69962-97b1-4a2a-b0cb-3df9a1035929" />

## Core Components and Deployment Models
IBM Granite AI foundation models
- The 20B parameter Granite base code model was used to train IBM watsonx Code Assistant (WCA).
- The 20B parameter Granite base code model powers watsonx Code Assistant for Z, which helps enterprises transform COBOL applications.
- IBM's Granite LLM was used to create the "Catch Me Up" feature, which provides personalized player stories and updates on Wimbledon matches.

**InstructLab**, an IBM and Red Hat open source project, based on the Large-scale Alignment for chatbBots (LAB) method and aims to enhance LLMs used in generative AI applications by making fine-tuning of foundation models straight-forward and accessible.

The LAB method allows users to customize an LLM with domain-specific knowledge and skills. InstructLab uses this to generate high-quality synthetic data that is used to train the LLM.

### AI & ML libraries in RHEL
support for popular open source AI/ML libraries like PyTorch and TensorFlow. 

- Hardware optimization
  - close integration with GPU, TPU and other accelerators, RHEL AI ensures machine learning models run with optimal performance.