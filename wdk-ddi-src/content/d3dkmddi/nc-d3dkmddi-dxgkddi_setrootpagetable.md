---
UID: NC:d3dkmddi.DXGKDDI_SETROOTPAGETABLE
title: DXGKDDI_SETROOTPAGETABLE
author: windows-driver-content
description: DxgkDdiSetRootPageTable sets the root page table for the given context. This function is used to notify a context when its associated root page table is resized or moved in memory.
old-location: display\dxgkddisetrootpagetable.htm
old-project: display
ms.assetid: BC9E7A2D-690D-4EC2-8D16-22C5FEBA574A
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_SETROOTPAGETABLE, DxgkDdiSetRootPageTable, DxgkDdiSetRootPageTable callback function [Display Devices], d3dkmddi/DxgkDdiSetRootPageTable, display.dxgkddisetrootpagetable, dispmprt/DxgkDdiSetRootPageTable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
-	d3dkmddi.h
api_name:
-	DxgkDdiSetRootPageTable
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_SETROOTPAGETABLE callback


## -description


<b>DxgkDdiSetRootPageTable</b> sets the root page table for the given context. This function is used to notify a context when its associated root page table is resized or moved in memory.


This is level 1 synchronization function. The targeted context is guaranteed to be idled (i.e. not scheduled) while its root page table is being updated.

  


## -prototype


````
DXGKDDI_SETROOTPAGETABLE DxgkDdiSetRootPageTable;

VOID APIENTRY DxgkDdiSetRootPageTable(
  _In_ const HANDLE                   hAdapter,
  _In_ const DXGKARG_SETROOTPAGETABLE *pSetPageTable
)
{ ... }
````


## -parameters




### -param hAdapter [in]

A handle to the display adapter.


### -param pSetPageTable [in]

The <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_setrootpagetable.md">DXGKARG_SETROOTPAGETABLE</a> structure that describes the operation.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_setrootpagetable.md">DXGKARG_SETROOTPAGETABLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_SETROOTPAGETABLE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

