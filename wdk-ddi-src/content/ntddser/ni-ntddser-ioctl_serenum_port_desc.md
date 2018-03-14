---
UID: NI:ntddser.IOCTL_SERENUM_PORT_DESC
title: IOCTL_SERENUM_PORT_DESC
author: windows-driver-content
description: The IOCTL_SERENUM_PORT_DESC request returns a description of the RS-232 port associated with a filter DO.
old-location: serports\ioctl_serenum_port_desc.htm
old-project: serports
ms.assetid: 9ecaa3fa-137d-4f79-9316-727ecab35da8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERENUM_PORT_DESC, IOCTL_SERENUM_PORT_DESC control code [Serial Ports], ntddser/IOCTL_SERENUM_PORT_DESC, senumref_2afa4ab9-ceac-4477-9ac6-10f572444e61.xml, serports.ioctl_serenum_port_desc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	ntddser.h
api_name:
-	IOCTL_SERENUM_PORT_DESC
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERENUM_PORT_DESC IOCTL


## -description


The <b>IOCTL_SERENUM_PORT_DESC</b> request returns a description of the RS-232 port associated with a filter DO.

This request is not implemented and is <b>obsolete</b>. The request must not be used in any Microsoft Windows drivers.


## -ioctlparameters




### -input-buffer



<text></text>




### -input-buffer-length



<text></text>




### -output-buffer



<text></text>




### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).



