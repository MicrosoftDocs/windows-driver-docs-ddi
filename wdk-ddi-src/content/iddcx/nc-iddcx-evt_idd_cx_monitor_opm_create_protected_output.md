---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT
title: EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT
author: windows-driver-content
description: EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT is called by the OS to create an OPM protected output context.
old-location: display\evt_idd_cx_monitor_opm_create_protected_output.htm
old-project: display
ms.assetid: 16c6fda5-c2e1-4ee4-80f7-e970b1da0e01
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT, EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT callback, EvtIddCxMonitorOpmCreateProtectedOutput, EvtIddCxMonitorOpmCreateProtectedOutput callback function [Display Devices], PFN_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT, PFN_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT callback function pointer [Display Devices], display.evt_idd_cx_monitor_opm_create_protected_output, iddcx/EvtIddCxMonitorOpmCreateProtectedOutput
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "_requires_same_"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	iddcx.h
api_name:
-	PFN_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT
product: Windows
targetos: Windows
req.typenames: 
---

# EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT callback function


## -description


<b>EVT_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT</b> is called by the OS to create an OPM protected output context.


## -parameters




### -param MonitorObject [in]


                    
                A handle used by the OS to identify the monitor that the OPM context should be created on.


### -param OpmCxtObject [in]


                    
                A context used by the OS to identify the OPM context the call is for.


### -param pInArgs [in]


                    
                Input arguments used by <b>EVT_IDD_CX_MONITOR_OPM CREATE_PROTECTED_OUTPUT</b>.


## -returns




(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 
                    



