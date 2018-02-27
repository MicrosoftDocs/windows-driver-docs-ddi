---
UID: NF:iddcx.IddCxDeviceInitConfig
title: IddCxDeviceInitConfig function
author: windows-driver-content
description: Creates a WDFDEVICE initialization structure to allow indirect displays to be used.
old-location: display\iddcxdeviceinitconfig.htm
old-project: display
ms.assetid: 4789e848-bb95-43e1-9768-8f94a475f9c8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IddCxDeviceInitConfig, IddCxDeviceInitConfig method [Display Devices], display.iddcxdeviceinitconfig, iddcx/IddCxDeviceInitConfig
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "_Must_inspect_result_"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IddCxDeviceInitConfig
product: Windows
targetos: Windows
req.typenames: 
---

# IddCxDeviceInitConfig function


## -description




                Creates a WDFDEVICE initialization structure to allow indirect displays to be used.


## -syntax


````
NTSTATUS IddCxDeviceInitConfig(
         PWDFDEVICE_INIT       DeviceInit,
   const IDD_CX_CLIENT_CONFIG* Config
);
````


## -parameters




### -param DeviceInit

The information about the device that is being initialized. 


### -param Config

The information required about the configuration of the client.


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    



