---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION
title: EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION
author: windows-driver-content
description: EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION is called by the OS to get OPM information.
old-location: display\evt_idd_cx_monitor_opm_get_infomation.htm
old-project: display
ms.assetid: b616a105-3c4b-42b7-8352-a1f35479572e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION, EvtIddCxMonitorOpmGetInfomation, EvtIddCxMonitorOpmGetInfomation callback function [Display Devices], PFN_IDD_CX_MONITOR_OPM_GET_INFOMATION, PFN_IDD_CX_MONITOR_OPM_GET_INFOMATION callback function pointer [Display Devices], display.evt_idd_cx_monitor_opm_get_infomation, iddcx/EvtIddCxMonitorOpmGetInfomation
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
-	PFN_IDD_CX_MONITOR_OPM_GET_INFOMATION
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION callback


## -description


<b>EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION</b> is called by the OS to get OPM information.


## -prototype


````
EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION EvtIddCxMonitorOpmGetInfomation;

NTSTATUS EvtIddCxMonitorOpmGetInfomation(
  _In_        IDDCX_OPMCTX                  OpmCxtObject,
  _In_  const IDARG_IN_OPM_GET_INFOMATION*  pInArgs,
  _Out_       IDARG_OUT_OPM_GET_INFOMATION* pOutArgs
)
{ ... }

typedef EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION PFN_IDD_CX_MONITOR_OPM_GET_INFOMATION;
````


## -parameters




### -param OpmCxtObject [in]


                    
                The object for the OPM context that information will be gotten from.


### -param pInArgs [in]


                    
                Input arguments used by <b>EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION</b>.


### -param pOutArgs [out]


                    
                Output arguments returned by <b>EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION</b>.


## -returns




(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 
                    



