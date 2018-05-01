---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ
title: IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ
author: windows-driver-content
description: IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ is sent by the Enhanced Storage Class Driver (EHSTOR) to the silo driver to initiate on-demand authentication or deauthentication.
old-location: storage\ioctl_ehstor_driver_perform_authz.htm
old-project: storage
ms.assetid: 689EE1EB-820A-4873-92C5-08F5F1873825
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ, IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ control, IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ, storage.ioctl_ehstor_driver_perform_authz
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	EhStorIoctl.h
api_name:
-	IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ IOCTL


## -description


<b>IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ</b> is sent by the Enhanced Storage Class Driver (EHSTOR) to the silo driver to initiate on-demand authentication or deauthentication.


## -ioctlparameters




### -input-buffer

The input buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> must contain an <b>AUTHZ_STATE</b> structure that indicates the type of authentication operation to perform. <b>AUTHZ_STATE</b> is declared in <i>ehstorioctl.h</i> as the following.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _AUTHZ_STATE
{
    ULONG AuthzState;
} AUTHZ_STATE;</pre>
</td>
</tr>
</table></span></div>
The value of <b>AuthzState</b> specifies the authentication operation. This is one of the following.

<table>
<tr>
<th> Value</th>
<th>Description</th>
</tr>
<tr>
<td>0</td>
<td>Perform on-demand deauthentication.</td>
</tr>
<tr>
<td>AUTHZSTATE_AUTHENTICATE</td>
<td>Perform on-demand authentication.</td>
</tr>
<tr>
<td>AUTHZSTATE_CLEAR_AUTHKEY_CACHE</td>
<td>Perform on-demand deauthentication and clear cached authentication keys.</td>
</tr>
</table>
 


### -input-buffer-length

The length of an <b>AUTHZ_STATE</b> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

STATUS_SUCCESS is returned in the <b>Status</b> field by the silo driver if the authentication state is changed. Otherwise, STATUS_UNSUCCESSFUL is returned.


## -remarks



This IOCTL is sent by EHSTOR to a silo driver that supports on-demand authentication. The silo driver notifies EHSTOR of this capability in a prior <a href="https://msdn.microsoft.com/library/windows/hardware/hh451445">IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a> request with the <b>CAP_ON_DEMAND_AUTHENTICATION</b> flag set in the <b>Capabilities</b> member of <a href="https://msdn.microsoft.com/32bb774f-b1eb-4198-8e4c-febcac83153d">SILO_DRIVER_CAPABILITES</a>. 

In response to this IOCTL, the silo driver performs authentication or deauthentication for the device. For banded devices, the silo driver will, depending on the specified operation in the system buffer, unlock or lock as many bands as possible for reads and writes.

If the silo driver fails to perform the requested operation, it will not change the authentication state of a device. 

If the <b>AuthzState</b> member of <b>AUTHZ_STATE</b> is set to <b>AUTHZSTATE_CLEAR_AUTHKEY_CACHE</b>, then the silo driver clears its authentication key cache in addition to deauthenticating. <b>AUTHZSTATE_CLEAR_AUTHKEY_CACHE</b> is set when the system is shutting down or hibernating. This prevents the presence of the  key cache in the hibernation file.

If a device supports multiple silos, authentication by each silo is exclusive. An authentication operation by one silo driver does not affect the authentication state set by another silo driver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451445">IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/32bb774f-b1eb-4198-8e4c-febcac83153d">SILO_DRIVER_CAPABILITES</a>
 

 

