[@cdklabs/generative-ai-cdk-constructs](../README.md) / [amazonaurora](../modules/amazonaurora.md) / AmazonAuroraDefaultVectorStoreProps

# Interface: AmazonAuroraDefaultVectorStoreProps

[amazonaurora](../modules/amazonaurora.md).AmazonAuroraDefaultVectorStoreProps

## Table of contents

### Properties

- [embeddingsModel](amazonaurora.AmazonAuroraDefaultVectorStoreProps.md#embeddingsmodel)

## Properties

### embeddingsModel

• `Readonly` **embeddingsModel**: [`BedrockFoundationModel`](../classes/bedrock.BedrockFoundationModel.md)

The embeddings model for the knowledge base.
Must be identical as in the KnowledgeBaseV2 construct.
This is due to the factor that the embeddings models
have different vector dimensions and this construct
needs to know the vector dimensions to create the vector
index of appropriate dimensions in the Aurora database.
