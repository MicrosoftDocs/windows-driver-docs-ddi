---
UID: NC:netdispumdddi.PFN_REPORT_SESSION_STATUS
title: PFN_REPORT_SESSION_STATUS
author: windows-driver-content
description: Called by the user-mode display driver to report the status of the current Miracast connected session.The data type of this function is PFN_REPORT_SESSION_STATUS.
old-location: display\reportsessionstatus.htm
old-project: display
ms.assetid: a3e44e55-5c6a-4a79-8caa-3a3b9db6b456
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFN_REPORT_SESSION_STATUS, ReportSessionStatus, ReportSessionStatus callback function [Display Devices], display.reportsessionstatus, netdispumdddi/ReportSessionStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Netdispumdddi.h
api_name:
-	ReportSessionStatus
product: Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---

# PFN_REPORT_SESSION_STATUS callback


## -description


Called by the user-mode display driver to report the status of the current Miracast connected session.The data type of this function is <b>PFN_REPORT_SESSION_STATUS</b>.




## -prototype


````
PFN_REPORT_SESSION_STATUS ReportSessionStatus;

VOID ReportSessionStatus(
  _In_ HANDLE          hMiracastDeviceHandle,
  _In_ MIRACAST_STATUS MiracastStatus,
  _In_ NTSTATUS        Status
)
{ ... }
````


## -parameters




### -param hMiracastDeviceHandle [in]

A handle that represents a Miracast device. The Miracast user-mode driver previously obtained this handle as the <i>hMiracastDeviceHandle</i> parameter in a call to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a> function.


### -param MiracastStatus [in]

The current status of the Miracast link, of type <a href="..\netdispumdddi\ne-netdispumdddi-miracast_status.md">MIRACAST_STATUS</a>.


### -param Status [in]

A status value the driver can provide that's logged for diagnostics purposes.


## -returns



Does not return a value.




## -remarks



If the Miracast user-mode driver reports an error in the <i>MiracastStatus</i> parameter, it initiates a tear-down of the current Miracast connected session.




## -see-also

<a href="..\netdispumdddi\ne-netdispumdddi-miracast_status.md">MIRACAST_STATUS</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a>



 

 


