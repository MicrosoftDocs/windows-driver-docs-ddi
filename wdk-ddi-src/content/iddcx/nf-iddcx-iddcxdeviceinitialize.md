---
UID: NF:iddcx.IddCxDeviceInitialize
title: IddCxDeviceInitialize function
description: Initializes a WDF device.
old-location: display\iddcxdeviceinitialize.htm
tech.root: display
ms.assetid: 4967e897-1a71-4f17-ad5b-9cc9916b0087
ms.date: 05/10/2018
ms.keywords: IddCxDeviceInitialize, IddCxDeviceInitialize method [Display Devices], display.iddcxdeviceinitialize, iddcx/IddCxDeviceInitialize
ms.topic: function
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: IddCxStub.lib 
req.dll: IddCx.dll 
req.irql: "_Must_inspect_result_"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	IddCx.dll
api_name:
-	IddCxDeviceInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# IddCxDeviceInitialize function


## -description


Initializes a WDF device

                


## -parameters




### -param Device [in]

The WDF device that is being initialized.


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    



