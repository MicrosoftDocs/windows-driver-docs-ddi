---
UID: NI:bthioctl.IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO
title: IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO
author: windows-driver-content
description: The IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO request obtains information about the underlying device and service that caused the Plug and Play (PnP) manager to load the profile driver.
old-location: bltooth\ioctl_internal_bthenum_get_enuminfo.htm
old-project: bltooth
ms.assetid: 43cd8e6b-5710-4308-a7c4-fb6f14940977
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO, IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO control code [Bluetooth Devices], bltooth.ioctl_internal_bthenum_get_enuminfo, bth_ioctls_110043d4-a637-4e7a-91d4-fd15a4c39a05.xml, bthioctl/IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bthioctl.h
api_name:
-	IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1
---

# IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO IOCTL


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
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536643">BTH_ENUMERATOR_INFO</a> structure that
      contains information about the enumeration's type and action, as well as information about the remote
      device.


### -output-buffer-length

The length of a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536643">BTH_ENUMERATOR_INFO</a> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536643">BTH_ENUMERATOR_INFO</a>
 

 

