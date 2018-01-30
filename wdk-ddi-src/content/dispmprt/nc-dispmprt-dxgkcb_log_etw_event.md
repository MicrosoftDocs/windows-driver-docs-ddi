---
UID: NC:dispmprt.DXGKCB_LOG_ETW_EVENT
title: DXGKCB_LOG_ETW_EVENT
author: windows-driver-content
description: The DxgkCbLogEtwEvent function logs an Event Tracing for Windows (ETW) event.
old-location: display\dxgkcblogetwevent.htm
old-project: display
ms.assetid: d869f933-4316-440e-899a-d46d72a0d10f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcblogetwevent, DxgkCbLogEtwEvent callback function [Display Devices], DxgkCbLogEtwEvent, DXGKCB_LOG_ETW_EVENT, DXGKCB_LOG_ETW_EVENT, dispmprt/DxgkCbLogEtwEvent, DpFunctions_1e074b6d-dff4-4d1f-93ce-4333a4241562.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: 
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dispmprt.h
apiname:
-	DxgkCbLogEtwEvent
product: Windows
targetos: Windows
req.typenames: "*PSYMBOL_INFO_EX, SYMBOL_INFO_EX"
---

# DXGKCB_LOG_ETW_EVENT callback


## -description


The <i>DxgkCbLogEtwEvent</i> function logs an Event Tracing for Windows (ETW) event. 


## -prototype


````
DXGKCB_LOG_ETW_EVENT DxgkCbLogEtwEvent;

VOID DxgkCbLogEtwEvent(
  _In_ const LPCGUID EventGuid,
  _In_       UCHAR   Type,
  _In_       USHORT  EventBufferSize,
  _In_       PVOID   EventBuffer
)
{ ... }
````


## -parameters




### -param LPCGUID



### -param Type [in]

A constant that specifies the event type. These constants  are defined in Evntrace.h and have the form of <b>EVENT_TRACE_TYPE_XX</b>.


### -param EventBufferSize [in]

The size, in bytes, of the buffer pointed to by <i>EventBuffer</i>. There is a significant performance penalty if the buffer is larger than 256 bytes.


### -param EventBuffer [in]

A pointer to a buffer that contains the information to be logged.


#### - EventGuid [in]

A GUID that identifies the event to be logged.


## -returns


None



## -remarks


If event logging is not enabled, <i>DxgkCbLogEtwEvent</i> returns immediately without logging the event.

To enable or disable event logging, call the <a href="..\dispmprt\nc-dispmprt-dxgkddi_control_etw_logging.md">DxgkDdiControlEtwLogging</a>  function.

If <i>EventBufferSize</i> is less than or equal to 256, <i>DxgkCbLogEtwEvent</i> can be called an any IRQL. If <i>EventBufferSize</i> is greater than 256, <i>DxgkCbLogEtwEvent</i> must be called at IRQL = PASSIVE_LEVEL.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_control_etw_logging.md">DxgkDdiControlEtwLogging</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_LOG_ETW_EVENT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

