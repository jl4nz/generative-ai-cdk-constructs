[@cdklabs/generative-ai-cdk-constructs](../README.md) / [amazonaurora](../modules/amazonaurora.md) / AmazonAuroraDefaultVectorStore

# Class: AmazonAuroraDefaultVectorStore

[amazonaurora](../modules/amazonaurora.md).AmazonAuroraDefaultVectorStore

Creates default AmazonAuroraVectorStore.

It includes creation of a VPC with 3 subnets (public,
private with NAT Gateway, private without NAT Gateway),
with the Amazon Aurora Serverless V2 Cluster.
The cluster has 1 writer/reader of PostgreSQL version 15.5
instance (min capacity 0.5, max capacity 4). Lambda custom
resource executes required pgvector and Amazon Bedrock Knowledge
Base SQL queries against Aurora cluster
during deployment. The secret containing databases credentials is
being deployed and securely stored in AWS Secrets Manager.
You must specify the same embeddings model that you used in
KnowledgeBase construct.

**`See`**

https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/AuroraPostgreSQL.VectorDB.html)

## Hierarchy

- `Resource`

  ↳ **`AmazonAuroraDefaultVectorStore`**

## Table of contents

### Constructors

- [constructor](amazonaurora.AmazonAuroraDefaultVectorStore.md#constructor)

### Properties

- [auroraPgCRPolicy](amazonaurora.AmazonAuroraDefaultVectorStore.md#aurorapgcrpolicy)
- [clusterIdentifier](amazonaurora.AmazonAuroraDefaultVectorStore.md#clusteridentifier)
- [credentialsSecretArn](amazonaurora.AmazonAuroraDefaultVectorStore.md#credentialssecretarn)
- [databaseName](amazonaurora.AmazonAuroraDefaultVectorStore.md#databasename)
- [embeddingsModel](amazonaurora.AmazonAuroraDefaultVectorStore.md#embeddingsmodel)
- [env](amazonaurora.AmazonAuroraDefaultVectorStore.md#env)
- [node](amazonaurora.AmazonAuroraDefaultVectorStore.md#node)
- [physicalName](amazonaurora.AmazonAuroraDefaultVectorStore.md#physicalname)
- [primaryKeyField](amazonaurora.AmazonAuroraDefaultVectorStore.md#primarykeyfield)
- [resourceArn](amazonaurora.AmazonAuroraDefaultVectorStore.md#resourcearn)
- [stack](amazonaurora.AmazonAuroraDefaultVectorStore.md#stack)
- [tableName](amazonaurora.AmazonAuroraDefaultVectorStore.md#tablename)

### Methods

- [\_enableCrossEnvironment](amazonaurora.AmazonAuroraDefaultVectorStore.md#_enablecrossenvironment)
- [applyRemovalPolicy](amazonaurora.AmazonAuroraDefaultVectorStore.md#applyremovalpolicy)
- [generatePhysicalName](amazonaurora.AmazonAuroraDefaultVectorStore.md#generatephysicalname)
- [getResourceArnAttribute](amazonaurora.AmazonAuroraDefaultVectorStore.md#getresourcearnattribute)
- [getResourceNameAttribute](amazonaurora.AmazonAuroraDefaultVectorStore.md#getresourcenameattribute)
- [toString](amazonaurora.AmazonAuroraDefaultVectorStore.md#tostring)
- [isConstruct](amazonaurora.AmazonAuroraDefaultVectorStore.md#isconstruct)
- [isOwnedResource](amazonaurora.AmazonAuroraDefaultVectorStore.md#isownedresource)
- [isResource](amazonaurora.AmazonAuroraDefaultVectorStore.md#isresource)

## Constructors

### constructor

• **new AmazonAuroraDefaultVectorStore**(`scope`, `id`, `props`): [`AmazonAuroraDefaultVectorStore`](amazonaurora.AmazonAuroraDefaultVectorStore.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `scope` | `Construct` |
| `id` | `string` |
| `props` | [`AmazonAuroraDefaultVectorStoreProps`](../interfaces/amazonaurora.AmazonAuroraDefaultVectorStoreProps.md) |

#### Returns

[`AmazonAuroraDefaultVectorStore`](amazonaurora.AmazonAuroraDefaultVectorStore.md)

#### Overrides

cdk.Resource.constructor

## Properties

### auroraPgCRPolicy

• `Private` **auroraPgCRPolicy**: `ManagedPolicy`

An IAM policy that allows Data API access to Aurora.

___

### clusterIdentifier

• `Readonly` **clusterIdentifier**: `string`

Cluster identifier of your Amazon Aurora DB cluster.

___

### credentialsSecretArn

• `Readonly` **credentialsSecretArn**: `string`

The Secret ARN of your Amazon Aurora DB cluster.

___

### databaseName

• `Readonly` **databaseName**: `string`

The name of your Database.

___

### embeddingsModel

• `Readonly` **embeddingsModel**: [`BedrockFoundationModel`](bedrock.BedrockFoundationModel.md)

Model used for embeddings.

___

### env

• `Readonly` **env**: `ResourceEnvironment`

#### Inherited from

cdk.Resource.env

___

### node

• `Readonly` **node**: `Node`

The tree node.

#### Inherited from

cdk.Resource.node

___

### physicalName

• `Protected` `Readonly` **physicalName**: `string`

Returns a string-encoded token that resolves to the physical name that
should be passed to the CloudFormation resource.

This value will resolve to one of the following:
- a concrete value (e.g. `"my-awesome-bucket"`)
- `undefined`, when a name should be generated by CloudFormation
- a concrete name generated automatically during synthesis, in
  cross-environment scenarios.

#### Inherited from

cdk.Resource.physicalName

___

### primaryKeyField

• `Readonly` **primaryKeyField**: `string`

Primary key of your Amazon Aurora DB cluster.

___

### resourceArn

• `Readonly` **resourceArn**: `string`

The ARN of your Amazon Aurora DB cluster.

___

### stack

• `Readonly` **stack**: `Stack`

#### Inherited from

cdk.Resource.stack

___

### tableName

• `Readonly` **tableName**: `string`

The Table Name of your Amazon Aurora DB cluster.

## Methods

### \_enableCrossEnvironment

▸ **_enableCrossEnvironment**(): `void`

Called when this resource is referenced across environments
(account/region) to order to request that a physical name will be generated
for this resource during synthesis, so the resource can be referenced
through its absolute name/arn.

#### Returns

`void`

#### Inherited from

cdk.Resource.\_enableCrossEnvironment

___

### applyRemovalPolicy

▸ **applyRemovalPolicy**(`policy`): `void`

Apply the given removal policy to this resource

The Removal Policy controls what happens to this resource when it stops
being managed by CloudFormation, either because you've removed it from the
CDK application or because you've made a change that requires the resource
to be replaced.

The resource can be deleted (`RemovalPolicy.DESTROY`), or left in your AWS
account for data recovery and cleanup later (`RemovalPolicy.RETAIN`).

#### Parameters

| Name | Type |
| :------ | :------ |
| `policy` | `RemovalPolicy` |

#### Returns

`void`

#### Inherited from

cdk.Resource.applyRemovalPolicy

___

### generatePhysicalName

▸ **generatePhysicalName**(): `string`

#### Returns

`string`

#### Inherited from

cdk.Resource.generatePhysicalName

___

### getResourceArnAttribute

▸ **getResourceArnAttribute**(`arnAttr`, `arnComponents`): `string`

Returns an environment-sensitive token that should be used for the
resource's "ARN" attribute (e.g. `bucket.bucketArn`).

Normally, this token will resolve to `arnAttr`, but if the resource is
referenced across environments, `arnComponents` will be used to synthesize
a concrete ARN with the resource's physical name. Make sure to reference
`this.physicalName` in `arnComponents`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `arnAttr` | `string` | The CFN attribute which resolves to the ARN of the resource. Commonly it will be called "Arn" (e.g. `resource.attrArn`), but sometimes it's the CFN resource's `ref`. |
| `arnComponents` | `ArnComponents` | The format of the ARN of this resource. You must reference `this.physicalName` somewhere within the ARN in order for cross-environment references to work. |

#### Returns

`string`

#### Inherited from

cdk.Resource.getResourceArnAttribute

___

### getResourceNameAttribute

▸ **getResourceNameAttribute**(`nameAttr`): `string`

Returns an environment-sensitive token that should be used for the
resource's "name" attribute (e.g. `bucket.bucketName`).

Normally, this token will resolve to `nameAttr`, but if the resource is
referenced across environments, it will be resolved to `this.physicalName`,
which will be a concrete name.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `nameAttr` | `string` | The CFN attribute which resolves to the resource's name. Commonly this is the resource's `ref`. |

#### Returns

`string`

#### Inherited from

cdk.Resource.getResourceNameAttribute

___

### toString

▸ **toString**(): `string`

Returns a string representation of this construct.

#### Returns

`string`

#### Inherited from

cdk.Resource.toString

___

### isConstruct

▸ **isConstruct**(`x`): x is Construct

Checks if `x` is a construct.

Use this method instead of `instanceof` to properly detect `Construct`
instances, even when the construct library is symlinked.

Explanation: in JavaScript, multiple copies of the `constructs` library on
disk are seen as independent, completely different libraries. As a
consequence, the class `Construct` in each copy of the `constructs` library
is seen as a different class, and an instance of one class will not test as
`instanceof` the other class. `npm install` will not create installations
like this, but users may manually symlink construct libraries together or
use a monorepo tool: in those cases, multiple copies of the `constructs`
library can be accidentally installed, and `instanceof` will behave
unpredictably. It is safest to avoid using `instanceof`, and using
this type-testing method instead.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `x` | `any` | Any object |

#### Returns

x is Construct

true if `x` is an object created from a class which extends `Construct`.

#### Inherited from

cdk.Resource.isConstruct

___

### isOwnedResource

▸ **isOwnedResource**(`construct`): `boolean`

Returns true if the construct was created by CDK, and false otherwise

#### Parameters

| Name | Type |
| :------ | :------ |
| `construct` | `IConstruct` |

#### Returns

`boolean`

#### Inherited from

cdk.Resource.isOwnedResource

___

### isResource

▸ **isResource**(`construct`): construct is Resource

Check whether the given construct is a Resource

#### Parameters

| Name | Type |
| :------ | :------ |
| `construct` | `IConstruct` |

#### Returns

construct is Resource

#### Inherited from

cdk.Resource.isResource
