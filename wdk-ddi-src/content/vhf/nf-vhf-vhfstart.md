---
UID: NF:vhf.VhfStart
title: VhfStart function (vhf.h)
description: The HID source driver calls this method to start the virtual HID device.
old-location: hid\vhfstart.htm
tech.root: hid
ms.assetid: F3DA4CBB-5749-4E7D-828F-398714575173
ms.date: 04/30/2018
keywords: ["VhfStart function"]
ms.keywords: VhfStart, VhfStart method [Human Input Devices], hid.vhfstart, vhf/VhfStart
f1_keywords:
 - "vhf/VhfStart"
 - "VhfStart"
req.header: vhf.h
req.include-header: 
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
req.lib: VhfKm.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- VhfKm.lib
- VhfKm.dll
api_name:
- VhfStart
targetos: Windows
req.typenames: 
---

# VhfStart function


## -description


The HID source driver calls this method to start the virtual HID device. 


## -parameters




### -param VhfHandle 
[in]
A handle to a virtual HID device that your HID source driver received in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vhf/nf-vhf-vhfcreate">VhfCreate</a>.


## -returns



If the <b>VhfStart</b> call succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS </a> value.




## -remarks



Virtual HID Framework (VHF) does not invoke any callback functions implemented by the HID source driver until the source driver calls <b>VhfStart</b>. A callback can get invoked before <b>VhfStart</b> returns.  After this call succeeds, the driver can  submit reports. The HID source driver must not invoke any VHF method until after <b>VhfStart</b> returns successfully



