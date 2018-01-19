---
UID: NS:wdm._MDL
title: _MDL
author: windows-driver-content
description: An MDL structure is a partially opaque structure that represents a memory descriptor list (MDL).
old-location: kernel\mdl.htm
old-project: kernel
ms.assetid: 71524333-dd5d-4f0b-8dd3-034ea926bc93
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _MDL, PMDL, MDL, *PMDLX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MDL
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.typenames: PMDL, MDL
req.product: Windows 10 or later.
---

# _MDL structure



## -description
An <b>MDL</b> structure is a partially opaque structure that represents a memory descriptor list (MDL).



## -syntax

````
struct MDL {
  PMDL Next;
};
````


## -struct-fields

### -field Next

Pointer to the next MDL in an MDL chain. For more information about MDL chains, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.


## -remarks
An MDL describes the layout of a virtual memory buffer in physical memory. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-mmgetmdlbytecount.md">MmGetMdlByteCount</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554533">MmGetMdlByteOffset</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554537">MmGetMdlPfnArray</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554568">MmInitializeMdl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MDL structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

