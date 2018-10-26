---
UID: NF:storport.StorPortGetDeviceObjects
title: StorPortGetDeviceObjects function
author: windows-driver-content
description: The StorPortGetDeviceObjects routine returns the device objects that are associated with the adapter device stack.
old-location: storage\storportgetdeviceobjects.htm
tech.root: storage
ms.assetid: e48b5048-5f5f-4efb-b7bf-2dd183074516
ms.date: 03/29/2018
ms.keywords: StorPortGetDeviceObjects, StorPortGetDeviceObjects routine [Storage Devices], storage.storportgetdeviceobjects, storport/StorPortGetDeviceObjects, storprt_219d8794-88c3-49c6-82ea-a19f75c3ad1f.xml
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortGetDeviceObjects
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortGetDeviceObjects function


## -description


The <b>StorPortGetDeviceObjects</b> routine returns the device objects that are associated with the adapter device stack. The device objects that will be returned are the functional and physical device objects of the adapter and the device object to which the functional device object is attached. 


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
 



