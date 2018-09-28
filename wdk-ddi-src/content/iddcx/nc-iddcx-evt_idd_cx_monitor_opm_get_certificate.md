---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE
title: EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE
author: windows-driver-content
description: EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE is called by the OS to get an OPM certificate.
old-location: display\evt_idd_cx_monitor_opm_get_certificate.htm
tech.root: display
ms.assetid: f1a3882e-7d45-4634-ae1d-fb8102716f36
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE, EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE callback, EvtIddCxMonitorOpmGetCertificate, EvtIddCxMonitorOpmGetCertificate callback function [Display Devices], PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE, PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE callback function pointer [Display Devices], display.evt_idd_cx_monitor_opm_get_certificate, iddcx/EvtIddCxMonitorOpmGetCertificate
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
-	PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE callback function


## -description


<b>EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE</b> is called by the OS to get an OPM certificate.


## -parameters




### -param AdapterObject [in]

The object for the adapter that the OPM certificate will be gotten for.


### -param pInArgs [in]

Input arguments used by <b>EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE</b>.


## -returns




(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 
                    



