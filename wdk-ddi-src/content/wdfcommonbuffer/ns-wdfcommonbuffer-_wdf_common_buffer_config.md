---
UID: NS:wdfcommonbuffer._WDF_COMMON_BUFFER_CONFIG
title: "_WDF_COMMON_BUFFER_CONFIG"
author: windows-driver-content
description: The WDF_COMMON_BUFFER_CONFIG structure contains configuration information for a common buffer.
old-location: wdf\wdf_common_buffer_config.htm
old-project: wdf
ms.assetid: 19e98448-6951-4eb4-bca1-8119cd6f7713
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_COMMON_BUFFER_CONFIG, wdfcommonbuffer/WDF_COMMON_BUFFER_CONFIG, *PWDF_COMMON_BUFFER_CONFIG, wdfcommonbuffer/PWDF_COMMON_BUFFER_CONFIG, kmdf.wdf_common_buffer_config, wdf.wdf_common_buffer_config, WDF_COMMON_BUFFER_CONFIG structure, PWDF_COMMON_BUFFER_CONFIG structure pointer, PWDF_COMMON_BUFFER_CONFIG, _WDF_COMMON_BUFFER_CONFIG, DFCommonBufferObjectRef_6b9d3f2e-8954-4777-b5e4-9828f73feec3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfcommonbuffer.h
req.include-header: WdfCommonBuffer.h
req.target-type: Windows
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
req.lib: 
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
-	WDF_COMMON_BUFFER_CONFIG
product: Windows
targetos: Windows
req.typenames: "*PWDF_COMMON_BUFFER_CONFIG, WDF_COMMON_BUFFER_CONFIG"
req.product: Windows 10 or later.
---

# _WDF_COMMON_BUFFER_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_COMMON_BUFFER_CONFIG</b> structure contains configuration information for a common buffer.


## -syntax


````
typedef struct _WDF_COMMON_BUFFER_CONFIG {
  ULONG Size;
  ULONG AlignmentRequirement;
} WDF_COMMON_BUFFER_CONFIG, *PWDF_COMMON_BUFFER_CONFIG;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field AlignmentRequirement

The alignment requirement for a common buffer. This value must be one less than the alignment boundary. For example, you can specify 15 for a 16-byte alignment boundary and 31 for a 32-byte alignment boundary. You can also use one of the FILE_<i>Xxxx</i>_ALIGNMENT constants that are defined in <i>Wdm.h</i>.   


## -remarks


The <b>WDF_COMMON_BUFFER_CONFIG</b> structure is used as input to the <a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffercreatewithconfig.md">WdfCommonBufferCreateWithConfig</a> method.

If your driver specifies an alignment requirement that is greater that the computer's page size (PAGE_SIZE), the logical addresses that the <a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress.md">WdfCommonBufferGetAlignedLogicalAddress</a> method returns are always aligned to the specified alignment requirement, but the virtual addresses that the <a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress.md">WdfCommonBufferGetAlignedVirtualAddress</a> method returns might not be aligned to the alignment requirement.

If your driver specifies an alignment requirement that is less than the computer's page size, all logical and virtual addresses are aligned to the specified alignment requirement.

For more information about specifying alignment requirements, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enabling-dma-transactions">Enabling DMA Transactions</a> and <a href="https://msdn.microsoft.com/81a56f62-917e-4798-b2cc-6469c802fab8">Using Common Buffers</a>.



## -see-also

<a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress.md">WdfCommonBufferGetAlignedLogicalAddress</a>

<a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffercreatewithconfig.md">WdfCommonBufferCreateWithConfig</a>

<a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress.md">WdfCommonBufferGetAlignedVirtualAddress</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_COMMON_BUFFER_CONFIG structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

