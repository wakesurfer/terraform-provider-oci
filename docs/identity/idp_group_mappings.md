# oci_identity_idp_group_mapping

## IdpGroupMapping Resource

### IdpGroupMapping Reference

The following attributes are exported:

* `compartment_id` - The OCID of the tenancy containing the `IdentityProvider`.
* `group_id` - The OCID of the IAM Service group that is mapped to the IdP group.
* `id` - The OCID of the `IdpGroupMapping`.
* `identity_provider_id` - The OCID of the `IdentityProvider` this mapping belongs to.
* `idp_group_name` - The name of the IdP group that is mapped to the IAM Service group.
* `inactive_state` - The detailed status of INACTIVE lifecycleState.
* `state` - The mapping's current state.
* `time_created` - Date and time the mapping was created, in the format defined by RFC3339.  Example: `2016-08-25T21:10:29.600Z` 



### Create Operation
Creates a single mapping between an IdP group and an IAM Service
[group](https://docs.us-phoenix-1.oraclecloud.com/api/#/en/identity/20160918/Group/).


The following arguments are supported:

* `group_id` - (Required) The OCID of the IAM Service [group](https://docs.us-phoenix-1.oraclecloud.com/api/#/en/identity/20160918/Group/) you want to map to the IdP group. 
* `identity_provider_id` - (Required) The OCID of the identity provider.
* `idp_group_name` - (Required) The name of the IdP group you want to map.


### Update Operation
Updates the specified group mapping.

The following arguments support updates:
* `group_id` - The OCID of the IAM Service [group](https://docs.us-phoenix-1.oraclecloud.com/api/#/en/identity/20160918/Group/) you want to map to the IdP group. 
* `idp_group_name` - The name of the IdP group you want to map.


** IMPORTANT **
Any change to a property that does not support update will force the destruction and recreation of the resource with the new property values

### Example Usage

```hcl
resource "oci_identity_idp_group_mapping" "test_idp_group_mapping" {
	#Required
	group_id = "${oci_identity_group.test_group.id}"
	identity_provider_id = "${oci_identity_identity_provider.test_identity_provider.id}"
	idp_group_name = "${var.idp_group_mapping_idp_group_name}"
}
```

# oci_identity_idp_group_mappings

## IdpGroupMapping DataSource

Gets a list of idp_group_mappings.

### List Operation
Lists the group mappings for the specified identity provider.

The following arguments are supported:

* `identity_provider_id` - (Required) The OCID of the identity provider.


The following attributes are exported:

* `idp_group_mappings` - The list of idp_group_mappings.

### Example Usage

```hcl
data "oci_identity_idp_group_mappings" "test_idp_group_mappings" {
	#Required
	identity_provider_id = "${oci_identity_identity_provider.test_identity_provider.id}"
}
```