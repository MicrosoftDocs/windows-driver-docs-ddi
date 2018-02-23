---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ
title: IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ
author: windows-driver-content
description: IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ is sent by the Enhanced Storage Class Driver (EHSTOR) to the silo driver to initiate on-demand authentication or deauthentication.
old-location: storage\ioctl_ehstor_driver_perform_authz.htm
old-project: storage
ms.assetid: 689EE1EB-820A-4873-92C5-08F5F1873825
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.ioctl_ehstor_driver_perform_authz, IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ control code [Storage Devices], IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ, ehstorioctl/IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	EhStorIoctl.h
apiname:
-	IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ
product: Windows
targetos: Windows
req.typenames: PDO_TYPE
---

# IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

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



This IOCTL is sent by EHSTOR to a silo driver that supports on-demand authentication. The silo driver notifies EHSTOR of this capability in a prior <a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_driver_report_capabilities.md">IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a> request with the <b>CAP_ON_DEMAND_AUTHENTICATION</b> flag set in the <b>Capabilities</b> member of <a href="..\ehstorioctl\ns-ehstorioctl-tagact_authz_state.md">SILO_DRIVER_CAPABILITES</a>. 

In response to this IOCTL, the silo driver performs authentication or deauthentication for the device. For banded devices, the silo driver will, depending on the specified operation in the system buffer, unlock or lock as many bands as possible for reads and writes.

If the silo driver fails to perform the requested operation, it will not change the authentication state of a device. 

If the <b>AuthzState</b> member of <b>AUTHZ_STATE</b> is set to <b>AUTHZSTATE_CLEAR_AUTHKEY_CACHE</b>, then the silo driver clears its authentication key cache in addition to deauthenticating. <b>AUTHZSTATE_CLEAR_AUTHKEY_CACHE</b> is set when the system is shutting down or hibernating. This prevents the presence of the  key cache in the hibernation file.

If a device supports multiple silos, authentication by each silo is exclusive. An authentication operation by one silo driver does not affect the authentication state set by another silo driver.




## -see-also

<a href="..\ehstorioctl\ns-ehstorioctl-tagact_authz_state.md">SILO_DRIVER_CAPABILITES</a>



<a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_driver_report_capabilities.md">IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

