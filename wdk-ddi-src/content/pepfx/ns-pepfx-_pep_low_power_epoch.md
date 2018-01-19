---
UID: NS:pepfx._PEP_LOW_POWER_EPOCH
title: _PEP_LOW_POWER_EPOCH
author: windows-driver-content
description: The PEP_LOW_POWER_EPOCH structure is used to provide data for a PEP_DPM_LOW_POWER_EPOCH notification (deprecated).
old-location: kernel\pep_low_power_epoch.htm
old-project: kernel
ms.assetid: 730312DE-5F11-46C8-8298-55AA5756C995
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _PEP_LOW_POWER_EPOCH, PEP_LOW_POWER_EPOCH, *PPEP_LOW_POWER_EPOCH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_LOW_POWER_EPOCH
req.alt-loc: pepfx.h
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
req.typenames: PEP_LOW_POWER_EPOCH, *PPEP_LOW_POWER_EPOCH
---

# _PEP_LOW_POWER_EPOCH structure



## -description
The <b>PEP_LOW_POWER_EPOCH</b> structure is used to provide data for a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186748">PEP_DPM_LOW_POWER_EPOCH</a> notification (deprecated).



## -syntax

````
typedef struct _PEP_LOW_POWER_EPOCH {
  BOOLEAN LowPowerEpoch;
} PEP_LOW_POWER_EPOCH, *PPEP_LOW_POWER_EPOCH;
````


## -struct-fields

### -field LowPowerEpoch

When <b>TRUE</b>, indicates that the low power epoch is on. 


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186748">PEP_DPM_LOW_POWER_EPOCH notification</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_LOW_POWER_EPOCH structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

