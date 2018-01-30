---
UID: NF:vhf.VhfStart
title: VhfStart function
author: windows-driver-content
description: The HID source driver calls this method to start the virtual HID device.
old-location: hid\vhfstart.htm
old-project: hid
ms.assetid: F3DA4CBB-5749-4E7D-828F-398714575173
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hid.vhfstart, VhfStart method [Human Input Devices], VhfStart, vhf/VhfStart
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	VhfKm.lib
-	VhfKm.dll
apiname:
-	VhfStart
product: Windows
targetos: Windows
req.typenames: "*PUSBSIDEBANDAUDIO_VOLUME_PARAMS, USBSIDEBANDAUDIO_VOLUME_PARAMS"
---

# VhfStart function


## -description


The HID source driver calls this method to start the virtual HID device. 


## -syntax


````
NTSTATUS VhfStart(
  [in] VHFHANDLE VhfHandle
);
````


## -parameters




### -param VhfHandle [in]

A handle to a virtual HID device that your HID source driver received in the previous call to <a href="..\vhf\nf-vhf-vhfcreate.md">VhfCreate</a>.


## -returns


If the <b>VhfStart</b> call succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS </a> value.



## -remarks


Virtual HID Framework (VHF) does not invoke any callback functions implemented by the HID source driver until the source driver calls <b>VhfStart</b>. A callback can get invoked before <b>VhfStart</b> returns.  After this call succeeds, the driver can  submit reports. The HID source driver must not invoke any VHF method until after <b>VhfStart</b> returns successfully


