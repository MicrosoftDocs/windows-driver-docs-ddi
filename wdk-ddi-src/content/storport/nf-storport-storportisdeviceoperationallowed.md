---
UID: NF:storport.StorPortIsDeviceOperationAllowed
title: StorPortIsDeviceOperationAllowed function (storport.h)
description: A miniport driver can call the StorPortIsDeviceOperationAllowedminiport routine to determine if operations for a certain device management class are allowed.
old-location: storage\storportisdeviceoperationallowed.htm
tech.root: storage
ms.assetid: 2FA71DC1-8068-42E3-A5C0-903858E496FA
ms.date: 03/29/2018
keywords: ["StorPortIsDeviceOperationAllowed function"]
ms.keywords: STORPORT_DEVICEOPERATION_SECURE_REPROVISION_GUID, StorPortIsDeviceOperationAllowed, StorPortIsDeviceOperationAllowed routine [Storage Devices], storage.storportisdeviceoperationallowed, storport/StorPortIsDeviceOperationAllowed
req.header: storport.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.1.
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
req.irql: IRQL == PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortIsDeviceOperationAllowed
 - storport/StorPortIsDeviceOperationAllowed
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortIsDeviceOperationAllowed
---

# StorPortIsDeviceOperationAllowed function


## -description

A miniport driver can call the <b>StorPortIsDeviceOperationAllowedminiport</b> routine to determine if operations for a certain device management      class are allowed. A status value is set in the return parameter to indicate whether such operations are allowed or not allowed for the device in its current operating environment.

## -parameters

### -param HwDeviceExtension 

[in]
A pointer to the hardware device extension for the host bus adapter (HBA).

### -param Address 

[in]
The address of a storage device unit.

### -param DeviceOperation 

[in]
A pointer to a GUID specifying a device management operation class. The following GUID is valid.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STORPORT_DEVICEOPERATION_SECURE_REPROVISION_GUID"></a><a id="storport_deviceoperation_secure_reprovision_guid"></a><dl>
<dt><b>STORPORT_DEVICEOPERATION_SECURE_REPROVISION_GUID</b></dt>
</dl>
</td>
<td width="60%">
The device is enabled to receive secured provisioning commands.

</td>
</tr>
</table>

### -param AllowedFlag 

[out]
 TRUE when the operation specified in <i>DeviceOperation</i> is allowed. Otherwise, FALSE.

## -returns

The <b>StorPortIsDeviceOperationAllowed</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
A valid value for <i>AllowedFlag</i> was returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<i>Address</i> points to an invalid unit address structure.

-or-

The storage device specified by <i>Address</i> is not found.

-or-

The pointer value in <i>AllowedFlag</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
The current IRQL > PASSIVE_LEVEL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
The management class specified in <i>DeviceOperation</i> is not available or invalid.

</td>
</tr>
</table>

