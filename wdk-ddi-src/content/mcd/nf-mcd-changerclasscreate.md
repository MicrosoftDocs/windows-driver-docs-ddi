---
UID: NF:mcd.ChangerClassCreate
title: ChangerClassCreate function
author: windows-driver-content
description: The ChangerClassCreateClose routine is called by a changer minidriver to allow the class driver perform device-independent operations needed to create or close a device.
old-location: storage\changerclasscreateclose.htm
old-project: storage
ms.assetid: 3abaf674-e8a8-42bb-ac31-1ca8f5e148e4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, ChangerClassCreate, ChangerClassCreateClose, ChangerClassCreateClose routine [Storage Devices], a, chgrclas_27002d62-809d-48db-a2fc-8603d376f0d2.xml, e, g, h, l, mcd/ChangerClassCreateClose, n, r, s, storage.changerclasscreateclose, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mcd.h
apiname:
-	ChangerClassCreateClose
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# ChangerClassCreate function


## -description


The <b>ChangerClassCreateClose</b> routine is called by a changer minidriver to allow the class driver perform device-independent operations needed to create or close a device. 


## -syntax


````
NTSTATUS ChangerClassCreateClose(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object of the device to be created or closed. 


### -param Irp [in]

Pointer to the I/O request packet (IRP) that initiated the create or close operation. 


## -returns



If the operation succeeds, the <b>ChangerClassCreateClose</b> routine returns STATUS_SUCCESS. Otherwise the routine returns one of the following status values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_SUCH_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
The device object does not have a properly initialized device extension.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_BUSY</b></dt>
</dl>
</td>
<td width="60%">
The device is already open. Only one open at a time is allowed.

</td>
</tr>
</table>
 



