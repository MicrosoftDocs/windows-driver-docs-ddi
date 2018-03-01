---
UID: NE:wudfddi_types._WDF_KPROCESSOR_MODE
title: "_WDF_KPROCESSOR_MODE"
author: windows-driver-content
description: The WDF_KPROCESSOR_MODE enumeration type identifies the processor modes in which a thread can execute.
old-location: wdf\wdf_kprocessor_mode.htm
old-project: wdf
ms.assetid: b50be4c2-4575-42b9-953d-9ddb3c3e696c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_KPROCESSOR_MODE, PWDF_KPROCESSOR_MODE, PWDF_KPROCESSOR_MODE enumeration pointer, WDF_KPROCESSOR_MODE, WDF_KPROCESSOR_MODE enumeration, WdfKProcessorModeInvalid, WdfKProcessorModeMaximum, WdfKernelMode, WdfUserMode, _WDF_KPROCESSOR_MODE, umdf.wdf_kprocessor_mode, umdfstructs_581a9b17-c059-4dc8-9784-8dce0d6a4e7d.xml, wdf.wdf_kprocessor_mode, wudfddi_types/PWDF_KPROCESSOR_MODE, wudfddi_types/WDF_KPROCESSOR_MODE, wudfddi_types/WdfKProcessorModeInvalid, wudfddi_types/WdfKProcessorModeMaximum, wudfddi_types/WdfKernelMode, wudfddi_types/WdfUserMode"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfddi_types.h
api_name:
-	WDF_KPROCESSOR_MODE
product: Windows
targetos: Windows
req.typenames: WDF_KPROCESSOR_MODE, *PWDF_KPROCESSOR_MODE
req.product: Windows 10 or later.
---

# _WDF_KPROCESSOR_MODE enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_KPROCESSOR_MODE</b> enumeration type identifies the processor modes in which a thread can execute.


## -syntax


````
typedef enum _WDF_KPROCESSOR_MODE { 
  WdfKProcessorModeInvalid  = 0,
  WdfKernelMode             = 1,
  WdfUserMode               = 2,
  WdfKProcessorModeMaximum  = 3
} WDF_KPROCESSOR_MODE, *PWDF_KPROCESSOR_MODE;
````


## -enum-fields




### -field WdfKProcessorModeInvalid

Reserved for system use.


### -field WdfKernelMode

The processor mode is kernel mode.


### -field WdfUserMode

The processor mode is user mode.


### -field WdfKProcessorModeMaximum

Valid enumeration values were exceeded.


## -remarks



The <b>WDF_KPROCESSOR_MODE</b> enumeration type is return type for <a href="https://msdn.microsoft.com/library/windows/hardware/ff559002">IWDFIoRequest2::GetRequestorMode</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559002">IWDFIoRequest2::GetRequestorMode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_KPROCESSOR_MODE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

