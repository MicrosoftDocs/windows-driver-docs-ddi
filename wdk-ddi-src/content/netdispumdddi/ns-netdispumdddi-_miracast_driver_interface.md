---
UID: NS:netdispumdddi._MIRACAST_DRIVER_INTERFACE
title: "_MIRACAST_DRIVER_INTERFACE"
author: windows-driver-content
description: Contains pointers to wireless display (Miracast) functions that are implemented by the Miracast user-mode driver.
old-location: display\miracast_driver_interface.htm
old-project: display
ms.assetid: a3b9695e-b317-471b-91de-e191c1f5cb17
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PMIRACAST_DRIVER_INTERFACE, MIRACAST_DRIVER_INTERFACE, MIRACAST_DRIVER_INTERFACE structure [Display Devices], PMIRACAST_DRIVER_INTERFACE, PMIRACAST_DRIVER_INTERFACE structure pointer [Display Devices], _MIRACAST_DRIVER_INTERFACE, display.miracast_driver_interface, netdispumdddi/MIRACAST_DRIVER_INTERFACE, netdispumdddi/PMIRACAST_DRIVER_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Netdispumdddi.h
apiname:
-	MIRACAST_DRIVER_INTERFACE
product: Windows
targetos: Windows
req.typenames: MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
---

# _MIRACAST_DRIVER_INTERFACE structure


## -description


Contains pointers to wireless display (Miracast) functions that are implemented by the Miracast user-mode driver.


## -syntax


````
typedef struct _MIRACAST_DRIVER_INTERFACE {
  UINT                         Size;
  PFN_CREATE_MIRACAST_CONTEXT  CreateMiracastContext;
  PFN_DESTROY_MIRACAST_CONTEXT DestroyMiracastContext;
  PFN_START_MIRACAST_SESSION   StartMiracastSession;
  PFN_STOP_MIRACAST_SESSION    StopMiracastSession;
  PFN_HANDLE_KMD_MESSAGE       HandleKernelModeMessage;
} MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE;
````


## -struct-fields




### -field Size

The size, in bytes, of the <b>MIRACAST_DRIVER_INTERFACE</b> structure that the driver returns when the operating system calls the <a href="..\netdispumdddi\nc-netdispumdddi-query_miracast_driver_interface.md">QueryMiracastDriverInterface</a> function.


### -field CreateMiracastContext

A pointer to the driver's  <a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a> function.


### -field DestroyMiracastContext

A pointer to the driver's  <a href="..\netdispumdddi\nc-netdispumdddi-pfn_destroy_miracast_context.md">DestroyMiracastContext</a> function.


### -field StartMiracastSession

A pointer to the driver's  <a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a> function.


### -field StopMiracastSession

A pointer to the driver's   <a href="..\netdispumdddi\nc-netdispumdddi-pfn_stop_miracast_session.md">StopMiracastSession</a> function.


### -field HandleKernelModeMessage

A pointer to the driver's  <a href="..\netdispumdddi\nc-netdispumdddi-pfn_handle_kmd_message.md">HandleKernelModeMessage</a> function.


## -see-also

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_handle_kmd_message.md">HandleKernelModeMessage</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_stop_miracast_session.md">StopMiracastSession</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_destroy_miracast_context.md">DestroyMiracastContext</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a>



<a href="..\netdispumdddi\nc-netdispumdddi-query_miracast_driver_interface.md">QueryMiracastDriverInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20MIRACAST_DRIVER_INTERFACE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

