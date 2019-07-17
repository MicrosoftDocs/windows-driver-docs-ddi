---
UID: NS:ntddstor._DEVICE_DSM_OFFLOAD_READ_PARAMETERS
title: _DEVICE_DSM_OFFLOAD_READ_PARAMETERS (ntddstor.h)
description: The DEVICE_DSM_OFFLOAD_READ_PARAMETERS structure specifies the parameters for an offload read action related to the data-set attributes for a device.
old-location: storage\device_dsm_offload_read_parameters.htm
tech.root: storage
ms.assetid: 4C0B2CFD-B981-4304-B3F9-AD534BF5A823
ms.date: 03/29/2018
ms.keywords: "*PDEVICE_DSM_OFFLOAD_READ_PARAMETERS, DEVICE_DSM_OFFLOAD_READ_PARAMETERS, DEVICE_DSM_OFFLOAD_READ_PARAMETERS structure [Storage Devices], PDEVICE_DSM_OFFLOAD_READ_PARAMETERS, PDEVICE_DSM_OFFLOAD_READ_PARAMETERS structure pointer [Storage Devices], _DEVICE_DSM_OFFLOAD_READ_PARAMETERS, ntddstor/DEVICE_DSM_OFFLOAD_READ_PARAMETERS, ntddstor/PDEVICE_DSM_OFFLOAD_READ_PARAMETERS, storage.device_dsm_offload_read_parameters"
ms.topic: struct
f1_keywords:
 - "ntddstor/DEVICE_DSM_OFFLOAD_READ_PARAMETERS"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddstor.h
api_name:
- DEVICE_DSM_OFFLOAD_READ_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DEVICE_DSM_OFFLOAD_READ_PARAMETERS, *PDEVICE_DSM_OFFLOAD_READ_PARAMETERS
---

# _DEVICE_DSM_OFFLOAD_READ_PARAMETERS structure


## -description


The <b>DEVICE_DSM_OFFLOAD_READ_PARAMETERS</b> structure specifies the parameters for an offload read action related to the data-set attributes for a device. 

This parameter structure is used in an offload read  action for an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request.  The <b>Action</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> structure is set to <b>DeviceDsmAction_OffloadRead</b>, and <b>ParameterBlockOffset</b> indicates the location of <b>DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS</b>.


## -struct-fields




### -field Flags

Not used. Set to 0.


### -field TimeToLive

The duration, in milliseconds, for which the requested data ranges should remain valid.


### -field Reserved

Reserved.


## -remarks



The <b>ParameterBlockOffset</b> and <b>ParameterBlockLength</b> members  of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> are set to the location and length of the  <b>DEVICE_DSM_OFFLOAD_READ_PARAMETERS</b> structure in the system buffer of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request.

The <b>DataSetRangesOffset</b> and <b>DataSetRangesLength</b> members of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> specify the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_data_set_range">DEVICE_DATA_SET_RANGE</a> structures for the extents of the offload read.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_data_set_range">DEVICE_DATA_SET_RANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_dsm_offload_write_parameters">DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>
 

 

