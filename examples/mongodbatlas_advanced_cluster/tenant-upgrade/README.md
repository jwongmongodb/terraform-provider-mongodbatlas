# MongoDB Atlas Provider -- Advanced Cluster Tenant Upgrade
This example creates a project and cluster. It is intended to show how to upgrade from shared, aka tenant, to dedicated tier.

Variables Required:
- `atlas_org_id`: ID of the Atlas organization
- `public_key`: Atlas public key
- `private_key`: Atlas  private key
- `provider_name`: Name of provider to use for cluster (TENANT, AWS, GCP)
- `backing_provider_name`: If provider_name is tenant, the backing provider (AWS, GCP)
- `provider_instance_size_name`: Size of the cluster (Free: M0, Dedicated: M10+.)

For this example, first we'll start out on the shared tier, then upgrade to a dedicated tier.

Utilize the following to execute a working example, replacing the org id, public and private key with your values:

Apply with the following `terraform.tfvars` to first create a shared tier cluster:
```
atlas_org_id                = <ATLAS_ORG_ID>
public_key                  = <ATLAS_PUBLIC_KEY>
private_key                 = <ATLAS_PRIVATE_KEY>
provider_name               = "TENANT"
backing_provider_name       = "AWS"
provider_instance_size_name = "M0"
```

Apply with the following `terraform.tfvars` to upgrade the shared tier cluster you just created to dedicated tier:
```
atlas_org_id                = <ATLAS_ORG_ID>
public_key                  = <ATLAS_PUBLIC_KEY>
private_key                 = <ATLAS_PRIVATE_KEY>
provider_name               = "AWS"
provider_instance_size_name = "M10"
