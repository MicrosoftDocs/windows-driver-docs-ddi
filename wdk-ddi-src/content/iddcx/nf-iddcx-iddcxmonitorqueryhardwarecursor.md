---
UID: NF:iddcx.IddCxMonitorQueryHardwareCursor
title: IddCxMonitorQueryHardwareCursor function
author: windows-driver-content
description: An OS callback function the driver calls when it wants obtain the updated cursor information. The driver normally only calls this when the event that signals cursor update has triggered.
old-location: display\iddcxmonitorqueryhardwarecursor.htm
old-project: display
ms.assetid: e954b7e7-9e4a-47ae-9b0f-8c7e051cc00e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IddCxMonitorQueryHardwareCursor, IddCxMonitorQueryHardwareCursor method [Display Devices], display.iddcxmonitorqueryhardwarecursor, iddcx/IddCxMonitorQueryHardwareCursor
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
req.lib: 
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
-	IddCxMonitorQueryHardwareCursor
product: Windows
targetos: Windows
req.typenames: 
---

# IddCxMonitorQueryHardwareCursor function


## -description




                 An OS callback function the driver calls when it wants obtain the updated cursor information. The driver normally only calls this when the event that signals cursor update has triggered


## -syntax


````
NTSTATUS IddCxMonitorQueryHardwareCursor(
  _In_        IDDCX_MONITOR             MonitorObject,
  _In_  const IDARG_IN_QUERY_HWCURSOR*  pInArgs,
  _Out_       IDARG_OUT_QUERY_HWCURSOR* pOutArgs
);
````


## -parameters




### -param MonitorObject [in]

This is the OS context handle for this monitor returned by the <a href="..\iddcx\nf-iddcx-iddcxmonitorarrival.md">IddCxMonitorArrival</a> call


### -param pInArgs [in]

Input arguments of the function


### -param pOutArgs [out]

Output arguments of the function


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    



