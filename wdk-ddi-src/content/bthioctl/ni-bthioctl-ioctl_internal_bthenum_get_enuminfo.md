---
UID: NI:bthioctl.IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO
title: IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO
author: windows-driver-content
description: The IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO request obtains information about the underlying device and service that caused the Plug and Play (PnP) manager to load the profile driver.
old-location: bltooth\ioctl_internal_bthenum_get_enuminfo.htm
old-project: bltooth
ms.assetid: 43cd8e6b-5710-4308-a7c4-fb6f14940977
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bltooth.ioctl_internal_bthenum_get_enuminfo, IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO control code [Bluetooth Devices], IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO, bthioctl/IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO, bth_ioctls_110043d4-a637-4e7a-91d4-fd15a4c39a05.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= PASSIVE_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bthioctl.h
apiname:
-	IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO
product: Windows
targetos: Windows
req.typenames: "*PHFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1"
---

# IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO request obtains information about the underlying device and
     service that caused the Plug and Play (PnP) manager to load the profile driver.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a 
      <a href="..\bthddi\ns-bthddi-_bth_enumerator_info.md">BTH_ENUMERATOR_INFO</a> structure that
      contains information about the enumeration's type and action, as well as information about the remote
      device.


### -output-buffer-length

The length of a 
      <a href="..\bthddi\ns-bthddi-_bth_enumerator_info.md">BTH_ENUMERATOR_INFO</a> structure.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also

<a href="..\bthddi\ns-bthddi-_bth_enumerator_info.md">BTH_ENUMERATOR_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

