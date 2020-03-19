---
UID: NF:iddcx.IddCxDeviceInitConfig
title: IddCxDeviceInitConfig function (iddcx.h)
description: Creates a WDFDEVICE initialization structure to allow indirect displays to be used.
old-location: display\iddcxdeviceinitconfig.htm
tech.root: display
ms.assetid: 4789e848-bb95-43e1-9768-8f94a475f9c8
ms.date: 05/10/2018
keywords: ["IddCxDeviceInitConfig function"]
ms.keywords: IddCxDeviceInitConfig, IddCxDeviceInitConfig method [Display Devices], display.iddcxdeviceinitconfig, iddcx/IddCxDeviceInitConfig
f1_keywords:
 - "iddcx/IddCxDeviceInitConfig"
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
req.irql: _Must_inspect_result_
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- IddCx.dll
api_name:
- IddCxDeviceInitConfig
product:
- Windows
targetos: Windows
req.typenames: 
---

# IddCxDeviceInitConfig function


## -description




                Creates a WDFDEVICE initialization structure to allow indirect displays to be used.


## -parameters




### -param DeviceInit

The information about the device that is being initialized. 


### -param Config

The information required about the configuration of the client.


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.
                    



