---
UID: NA:ehstorbandmgmt
ms.assetid: 5620fe38-a1b7-3b18-8f1d-4366b8866138
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ehstorbandmgmt.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Ehstorbandmgmt.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_BAND_LOCATION_INFO structure](ns-ehstorbandmgmt-_band_location_info.md) | The BAND_LOCATION_INFO structure specifies the location information for a band table entry query. |
| [_BAND_MANAGEMENT_CAPABILITIES structure](ns-ehstorbandmgmt-_band_management_capabilities.md) | The BAND_MANAGEMENT_CAPABILITIES structure contains the security capabilities available for a storage device. This structure is returned in the system buffer by the IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES request. |
| [_BAND_SECURITY_INFO structure](ns-ehstorbandmgmt-_band_security_info.md) | The BAND_SECURITY_INFO structure specifies the security information for a band table entry query. |
| [_BAND_TABLE structure](ns-ehstorbandmgmt-_band_table.md) | The BAND_TABLE structure contains the table of bands returned from an IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS request. |
| [_BAND_TABLE_ENTRY structure](ns-ehstorbandmgmt-_band_table_entry.md) | Banding information entries in BAND_TABLE are represented as BAND_TABLE_ENTRY structures. These entries contain location and security properties for a band configuration. |
| [_CREATE_BAND_PARAMETERS structure](ns-ehstorbandmgmt-_create_band_parameters.md) | The parameters to create a band on a storage device for an IOCTL_EHSTOR_BANDMGMT_CREATE_BAND request are specified in a CREATE_BAND_PARAMETERS structure. |
| [_DELETE_BAND_PARAMETERS structure](ns-ehstorbandmgmt-_delete_band_parameters.md) | A configured band is deleted according to the parameters in a DELETE_BAND_PARAMETERS structure. This structure is input for an IOCTL_EHSTOR_BANDMGMT_DELETE_BAND request. |
| [_ENUMERATE_BANDS_PARAMETERS structure](ns-ehstorbandmgmt-_enumerate_bands_parameters.md) | The ENUMERATE_BANDS_PARAMETERS structure is used to select which band information entries are selected for return from an IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS request. |
| [_ERASE_BAND_PARAMETERS structure](ns-ehstorbandmgmt-_erase_band_parameters.md) | The ERASE_BAND_PARAMETERS structure contains the selection criteria for a band to erase. Additionally, a new authentication key can be set. This structure is input for an IOCTL_EHSTOR_BANDMGMT_ERASE_BAND request. |
| [_GET_BAND_METADATA_PARAMETERS structure](ns-ehstorbandmgmt-_get_band_metadata_parameters.md) | The metadata for a configured band is retrieved according to the parameters in a GET_BAND_METADATA_PARAMETERS structure. This structure is input for an IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA request. |
| [_SET_BAND_LOCATION_PARAMETERS structure](ns-ehstorbandmgmt-_set_band_location_parameters.md) | The SET_BAND_LOCATION_PARAMETERS structure specifies the parameters to set location properties for a band on a storage device for a IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION request. |
| [_SET_BAND_METADATA_PARAMETERS structure](ns-ehstorbandmgmt-_set_band_metadata_parameters.md) | The metadata for a configured band is set to the parameters in a SET_BAND_METADATA_PARAMETERS structure. This structure is input for a IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA request. |
| [_SET_BAND_SECURITY_PARAMETERS structure](ns-ehstorbandmgmt-_set_band_security_parameters.md) | The parameters to set security properties for a band on a storage device for a IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY request are specified in a SET_BAND_SECURITY_PARAMETERS structure. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_EHSTOR_BANDMGMT_ACTIVATE IOCTL](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_activate.md) | This IOCTL_EHSTOR_BANDMGMT_ACTIVATE request is sent to activate the security features and band management on a storage device. The request includes activation options and the authentication key. |
| [IOCTL_EHSTOR_BANDMGMT_CREATE_BAND IOCTL](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_create_band.md) | New bands are created on a band-managed storage device with the IOCTL_EHSTOR_BANDMGMT_CREATE_BAND request. A new band is added to the table of band entries, which includes band location and security properties. |
| [IOCTL_EHSTOR_BANDMGMT_DELETE_BAND IOCTL](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_delete_band.md) | A configured band on a storage device is deleted with the IOCTL_EHSTOR_BANDMGMT_DELETE_BAND request. An erase option in the input parameters allows the request to perform a cryptographic erase of the band data. |
| [IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS IOCTL](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands.md) | This IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS request is sent to retrieve the list of bands for a storage device under band management. Banding information is returned in a table of band entries that includes band location and security properties. |
| [IOCTL_EHSTOR_BANDMGMT_ERASE_BAND IOCTL](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_erase_band.md) | The IOCTL_EHSTOR_BANDMGMT_ERASE_BAND request will cryptographically erase and reset the authentication key of a band. The remaining configuration of the band is left unmodified. |
| [IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA IOCTL](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_get_band_metadata.md) | Metadata associated with a band is retrieved with an IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA request. The metadata for a band serves as a data area for a key manager application. |
| [IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES IOCTL](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_query_capabilities.md) | The IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES request retrieves the banded security capabilities for a storage device. The IOCTL returns the capabilities as a BAND_MANAGEMENT_CAPABILITIES structure in the system buffer. |
| [IOCTL_EHSTOR_BANDMGMT_REVERT IOCTL](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_revert.md) | This IOCTL_EHSTOR_BANDMGMT_REVERT request is sent to deactivate the security features and band management on a storage device. The request includes revert options and the authentication key. |
| [IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION IOCTL](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_set_band_location.md) | The location properties of bands in a band-managed storage device are modified with the IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION request. |
| [IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA IOCTL](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_set_band_metadata.md) | Metadata associated with a band is set with an IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA request. The metadata for a band serves as a data area for a key manager application. |
| [IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY IOCTL](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_set_band_security.md) | The security properties of bands in a band-managed storage device are modified with the IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY request. |
| [IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO IOCTL](ni-ehstorbandmgmt-ioctl_ehstor_tcgdrv_relinquish_silo.md) | The IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO request relinquishes control of band management by the Trusted Computing Group (TCG) Storage Silo driver. |
