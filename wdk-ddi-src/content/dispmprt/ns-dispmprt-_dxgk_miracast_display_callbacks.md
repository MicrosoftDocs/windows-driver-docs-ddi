---
UID: NS:dispmprt._DXGK_MIRACAST_DISPLAY_CALLBACKS
title: "_DXGK_MIRACAST_DISPLAY_CALLBACKS"
author: windows-driver-content
description: Contains pointers to functions in the Wireless display (Miracast) display callback interface that the display miniport driver can call to send messages and report encode chunk info.
old-location: display\dxgk_miracast_display_callbacks.htm
old-project: display
ms.assetid: C60F03A1-AD90-43C7-99DF-5EC45151D1F5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "*PDXGK_MIRACAST_DISPLAY_CALLBACKS, _DXGK_MIRACAST_DISPLAY_CALLBACKS, dispmprt/PDXGK_MIRACAST_DISPLAY_CALLBACKS, dispmprt/DXGK_MIRACAST_DISPLAY_CALLBACKS, DXGK_MIRACAST_DISPLAY_CALLBACKS, PDXGK_MIRACAST_DISPLAY_CALLBACKS structure pointer [Display Devices], display.dxgk_miracast_display_callbacks, DXGK_MIRACAST_DISPLAY_CALLBACKS structure [Display Devices], PDXGK_MIRACAST_DISPLAY_CALLBACKS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Dispmprt.h
apiname:
-	DXGK_MIRACAST_DISPLAY_CALLBACKS
product: Windows
targetos: Windows
req.typenames: DXGK_MIRACAST_DISPLAY_CALLBACKS, *PDXGK_MIRACAST_DISPLAY_CALLBACKS
---

# _DXGK_MIRACAST_DISPLAY_CALLBACKS structure


## -description


Contains pointers to functions in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn344650">Wireless display (Miracast) display callback interface</a> that the display miniport driver can call to send messages and report encode chunk info.


## -syntax


````
typedef struct _DXGK_MIRACAST_DISPLAY_CALLBACKS {
  HANDLE                            MiracastHandle;
  DXGKCB_MIRACAST_SEND_MESSAGE      DxgkCbMiracastSendMessage;
  DXGKCB_MIRACAST_REPORT_CHUNK_INFO DxgkCbReportChunkInfo;
} DXGK_MIRACAST_DISPLAY_CALLBACKS, *PDXGK_MIRACAST_DISPLAY_CALLBACKS;
````


## -struct-fields




### -field MiracastHandle

A driver-supplied handle to the Miracast display device.


### -field DxgkCbMiracastSendMessage

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_miracast_send_message.md">DxgkCbMiracastSendMessage</a> function.


### -field DxgkCbReportChunkInfo

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_miracast_report_chunk_info.md">DxgkCbReportChunkInfo</a> function.


## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkcb_miracast_report_chunk_info.md">DxgkCbReportChunkInfo</a>



<a href="..\dispmprt\nc-dispmprt-dxgkcb_miracast_send_message.md">DxgkCbMiracastSendMessage</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_MIRACAST_DISPLAY_CALLBACKS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

