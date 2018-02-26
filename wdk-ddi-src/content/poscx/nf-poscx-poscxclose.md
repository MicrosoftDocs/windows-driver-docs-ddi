---
UID: NF:poscx.PosCxClose
title: PosCxClose function
author: windows-driver-content
description: PosCxClose is called to delete an opened PosCx library instance. This function releases the device if the caller is the owner, and cancels pending requests. It should be called from the driver's EVT_WDF_FILE_CLOSE callback.
old-location: pos\poscxclose.htm
old-project: pos
ms.assetid: 90D097B9-EE7B-49FA-B0F7-6A255D140C06
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , C, P, PosCxClose, PosCxClose function, e, l, o, pos.poscxclose, poscx/PosCxClose, s, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	poscx.h
apiname:
-	PosCxClose
product: Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---

# PosCxClose function


## -description


      PosCxClose is called to delete an opened PosCx library instance. This function releases the device if the caller is the owner, 

      and cancels pending requests. It should be called from 

      the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_close.md">EVT_WDF_FILE_CLOSE</a> callback.


## -syntax


````
NTSTATUS PosCxClose(
  _In_ WDFDEVICE     device,
  _In_ WDFFILEOBJECT fileObject
);
````


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param fileObject [in]

      A handle to a framework file object that identifies the caller associated with the open instance.


## -returns



An appropriate NTSTATUS error code that indicates the close instance completion status.



