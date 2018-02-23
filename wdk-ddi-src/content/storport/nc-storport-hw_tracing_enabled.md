---
UID: NC:storport.HW_TRACING_ENABLED
title: HW_TRACING_ENABLED
author: windows-driver-content
description: The HwStorTracingEnabled callback routine enables the Storport to notify a miniport that event tracing is enabled.
old-location: storage\hwstortracingenabled.htm
old-project: storage
ms.assetid: 2B56A2D3-1FA6-4212-A83C-3C20D826353B
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.hwstortracingenabled, HwStorTracingEnabled routine [Storage Devices], HwStorTracingEnabled, HW_TRACING_ENABLED, HW_TRACING_ENABLED, storport/HwStorTracingEnabled
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Storport.h
apiname:
-	HwStorTracingEnabled
product: Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
req.product: Windows 10 or later.
---

# HW_TRACING_ENABLED callback


## -description


The <b>HwStorTracingEnabled</b> callback routine enables the Storport to notify a miniport that event tracing is enabled. 


## -prototype


````
HW_TRACING_ENABLED HwStorTracingEnabled;

VOID HwStorTracingEnabled(
  _In_ PVOID   DeviceExtension,
  _In_ BOOLEAN Enabled
)
{ ... }
````


## -parameters




### -param HwDeviceExtension


### -param Enabled [in]

True to enable tracing in the miniport. Otherwise, false.


#### - DeviceExtension [in]

A pointer to the miniport driver's per-HBA storage area. 


## -returns



None.




## -remarks



The name <i>HwStorTracingEnabled</i> is placeholder text for the actual routine name. The actual prototype of this routine is defined in <i>Storport.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_TRACING_ENABLED (
    _In_ PVOID HwDeviceExtension,
    _In_ BOOLEAN Enabled
    );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HW_TRACING_ENABLED routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

