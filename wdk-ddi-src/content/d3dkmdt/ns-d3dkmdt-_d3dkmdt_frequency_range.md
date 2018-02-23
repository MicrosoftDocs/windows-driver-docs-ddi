---
UID: NS:d3dkmdt._D3DKMDT_FREQUENCY_RANGE
title: "_D3DKMDT_FREQUENCY_RANGE"
author: windows-driver-content
description: The D3DKMDT_FREQUENCY_RANGE structure contains the minimum and maximum refresh rates supported by a monitor.
old-location: display\d3dkmdt_frequency_range.htm
old-project: display
ms.assetid: f826f949-b37f-4c48-80d9-b6ef640e1f00
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_D3DKMDT_FREQUENCY_RANGE, d3dkmdt/D3DKMDT_FREQUENCY_RANGE, display.d3dkmdt_frequency_range, D3DKMDT_FREQUENCY_RANGE, D3DKMDT_FREQUENCY_RANGE structure [Display Devices], DmStructs_63b22220-c9fc-4eac-a725-caa0f5c38eba.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dkmdt.h
apiname:
-	D3DKMDT_FREQUENCY_RANGE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_FREQUENCY_RANGE
---

# _D3DKMDT_FREQUENCY_RANGE structure


## -description


The D3DKMDT_FREQUENCY_RANGE structure contains the minimum and maximum refresh rates supported by a monitor.


## -syntax


````
typedef struct _D3DKMDT_FREQUENCY_RANGE {
  D3DDDI_RATIONAL MinVSyncFreq;
  D3DDDI_RATIONAL MaxVSyncFreq;
  D3DDDI_RATIONAL MinHSyncFreq;
  D3DDDI_RATIONAL MaxHSyncFreq;
} D3DKMDT_FREQUENCY_RANGE;
````


## -struct-fields




### -field MinVSyncFreq

The minimum vertical refresh rate, in Hz, supported by the monitor.


### -field MaxVSyncFreq

The maximum vertical refresh rate, in Hz, supported by the monitor.


### -field MinHSyncFreq

The minimum horizontal refresh rate, in Hz, supported by the monitor.


### -field MaxHSyncFreq

The maximum horizontal refresh rate, in Hz, supported by the monitor.


## -remarks



The <b>RangeLimits</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_frequency_range.md">D3DKMDT_MONITOR_FREQUENCY_RANGE</a> structure is a D3DKMDT_FREQUENCY_RANGE structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568430">Monitor Frequency Range Set Interface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_FREQUENCY_RANGE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

