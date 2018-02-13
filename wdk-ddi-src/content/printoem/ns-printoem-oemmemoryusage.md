---
UID: NS:printoem.OEMMEMORYUSAGE
title: OEMMEMORYUSAGE
author: windows-driver-content
description: The OEMMEMORYUSAGE structure is used as an input parameter to a rendering plug-in's IPrintOemUni::MemoryUsage method.
old-location: print\oemmemoryusage.htm
old-project: print
ms.assetid: a7a522b8-7aa2-45b6-9200-407471dca82f
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: OEMMEMORYUSAGE, OEMMEMORYUSAGE structure [Print Devices], print.oemmemoryusage, printoem/POEMMEMORYUSAGE, *POEMMEMORYUSAGE, printoem/OEMMEMORYUSAGE, POEMMEMORYUSAGE structure pointer [Print Devices], POEMMEMORYUSAGE, print_unidrv-pscript_rendering_c6746c1c-f6c5-4acf-bcd3-bc1f69382dae.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEMMEMORYUSAGE
product: Windows
targetos: Windows
req.typenames: OEMMEMORYUSAGE, *POEMMEMORYUSAGE
req.product: Windows 10 or later.
---

# OEMMEMORYUSAGE structure


## -description


The OEMMEMORYUSAGE structure is used as an input parameter to a rendering plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554264">IPrintOemUni::MemoryUsage</a> method.


## -syntax


````
typedef struct {
  DWORD dwFixedMemoryUsage;
  DWORD dwPercentMemoryUsage;
  DWORD dwMaxBandSize;
} OEMMEMORYUSAGE, *POEMMEMORYUSAGE;
````


## -struct-fields




### -field dwFixedMemoryUsage

Specifies the amount, in bytes, of fixed-sized memory required by the <b>IPrintOemUni::MemoryUsage</b> method. Supplied by the rendering plug-in.


### -field dwPercentMemoryUsage

Specifies the amount of variably-sized memory required by the <b>IPrintOemUni::MemoryUsage</b> method, expressed as a percentage of the size of the source bitmap received by <a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a>. Supplied by the rendering plug-in.


### -field dwMaxBandSize

Specifies the maximum size, in bytes, that can be used for source bitmaps. This is the value that Unidrv uses to subtract from when applying the plug-in supplied values contained in <b>dwFixedMemoryUsage</b> and <b>dwPercentMemoryUsage</b>. Supplied by Unidrv.


## -remarks



The Unidrv driver uses the values in the <b>dwFixedMemoryUsage</b> and <b>dwPercentMemoryUsage</b> members of this structure to determine the optimum size for a GDI drawing surface, taking into account any memory requirements of a rendering plug-in's <b>IPrintOemUni::ImageProcessing</b> method. For more information about how these members are used, see the Remarks section in <a href="https://msdn.microsoft.com/library/windows/hardware/ff554264">IPrintOemUni::MemoryUsage</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554264">IPrintOemUni::MemoryUsage</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20OEMMEMORYUSAGE structure%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

