---
UID: NF:iddcx.IddCxMonitorUpdateModes
title: IddCxMonitorUpdateModes function
author: windows-driver-content
description: An OS callback function the driver calls to update the mode list.
old-location: display\iddcxmonitorupdatemodes.htm
old-project: display
ms.assetid: 0f05931a-2327-454a-9ba7-da02cb2f13d9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IddCxMonitorUpdateModes, IddCxMonitorUpdateModes method [Display Devices], display.iddcxmonitorupdatemodes, iddcx/IddCxMonitorUpdateModes
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
-	IddCxMonitorUpdateModes
product: Windows
targetos: Windows
req.typenames: 
---

# IddCxMonitorUpdateModes function


## -description




                An OS callback function the driver calls to update the mode list


## -syntax


````
NTSTATUS IddCxMonitorUpdateModes(
  _In_       IDDCX_MONITOR         MonitorObject,
  _In_ const IDARG_IN_UPDATEMODES* pInArgs
);
````


## -parameters




### -param MonitorObject [in]

The monitor object being updated


### -param pInArgs [in]

Input arguments of function 


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    



