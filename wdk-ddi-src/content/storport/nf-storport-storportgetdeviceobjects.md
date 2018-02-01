---
UID: NF:storport.StorPortGetDeviceObjects
title: StorPortGetDeviceObjects function
author: windows-driver-content
description: The StorPortGetDeviceObjects routine returns the device objects that are associated with the adapter device stack.
old-location: storage\storportgetdeviceobjects.htm
old-project: storage
ms.assetid: e48b5048-5f5f-4efb-b7bf-2dd183074516
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.storportgetdeviceobjects, storport/StorPortGetDeviceObjects, StorPortGetDeviceObjects routine [Storage Devices], StorPortGetDeviceObjects, storprt_219d8794-88c3-49c6-82ea-a19f75c3ad1f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
-	storport.h
apiname:
-	StorPortGetDeviceObjects
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortGetDeviceObjects function


## -description


The <b>StorPortGetDeviceObjects</b> routine returns the device objects that are associated with the adapter device stack. The device objects that will be returned are the functional and physical device objects of the adapter and the device object to which the functional device object is attached. 


## -syntax


````
ULONG StorPortGetDeviceObjects(
  _In_  PVOID HwDeviceExtension,
  _Out_ PVOID *AdapterDeviceObject,
  _Out_ PVOID *PhysicalDeviceObject,
  _Out_ PVOID *LowerDeviceObject
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param AdapterDeviceObject [out]

A pointer to receive the functional device object (FDO) of the adapter.


### -param PhysicalDeviceObject [out]

A pointer to receive the physical device object (PDO).


### -param LowerDeviceObject [out]

A pointer to receive the device object of lower device to which the FDO is attached.


## -returns


<b>StorPortGetDeviceObjects</b> returns one of the following status codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the device objects were obtained successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>HwDeviceExtension</i> was <b>NULL</b>.

</td>
</tr>
</table> 


