---
UID: NF:wdfcommonbuffer.WDF_COMMON_BUFFER_CONFIG_INIT
title: WDF_COMMON_BUFFER_CONFIG_INIT function
author: windows-driver-content
description: The WDF_COMMON_BUFFER_CONFIG_INIT function initializes a WDF_COMMON_BUFFER_CONFIG structure.
old-location: wdf\wdf_common_buffer_config_init.htm
old-project: wdf
ms.assetid: a678516a-159f-42bc-b135-489677452472
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_COMMON_BUFFER_CONFIG_INIT, DFCommonBufferObjectRef_23c5b41e-89ce-448c-86fa-3ae4e688b378.xml, kmdf.wdf_common_buffer_config_init, wdf.wdf_common_buffer_config_init, wdfcommonbuffer/WDF_COMMON_BUFFER_CONFIG_INIT, WDF_COMMON_BUFFER_CONFIG_INIT function
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcommonbuffer.h
req.include-header: WdfCommonBuffer.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfcommonbuffer.h
apiname:
-	WDF_COMMON_BUFFER_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: WDF_CHILD_RETRIEVE_INFO, *PWDF_CHILD_RETRIEVE_INFO
req.product: Windows 10 or later.
---

# WDF_COMMON_BUFFER_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_COMMON_BUFFER_CONFIG_INIT</b> function initializes a <a href="..\wdfcommonbuffer\ns-wdfcommonbuffer-_wdf_common_buffer_config.md">WDF_COMMON_BUFFER_CONFIG</a> structure.


## -syntax


````
VOID WDF_COMMON_BUFFER_CONFIG_INIT(
  _Out_ PWDF_COMMON_BUFFER_CONFIG Config,
  _In_  ULONG                     AlignmentRequirement
);
````


## -parameters




### -param Config [out]

A pointer to a <a href="..\wdfcommonbuffer\ns-wdfcommonbuffer-_wdf_common_buffer_config.md">WDF_COMMON_BUFFER_CONFIG</a> structure.


### -param AlignmentRequirement [in]

A value for the <b>AlignmentRequirement</b> member of the <a href="..\wdfcommonbuffer\ns-wdfcommonbuffer-_wdf_common_buffer_config.md">WDF_COMMON_BUFFER_CONFIG</a> structure. This value specifies the alignment requirement for the common buffer that the structure describes.


## -returns



None




## -remarks



The <b>WDF_COMMON_BUFFER_CONFIG_INIT</b> function zeros the specified <a href="..\wdfcommonbuffer\ns-wdfcommonbuffer-_wdf_common_buffer_config.md">WDF_COMMON_BUFFER_CONFIG</a> structure and sets the structure's <b>AlignmentRequirement</b> member to the specified value.




## -see-also

<a href="..\wdfcommonbuffer\ns-wdfcommonbuffer-_wdf_common_buffer_config.md">WDF_COMMON_BUFFER_CONFIG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_COMMON_BUFFER_CONFIG_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

