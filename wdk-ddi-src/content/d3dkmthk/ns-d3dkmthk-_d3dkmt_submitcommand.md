---
UID: NS:d3dkmthk._D3DKMT_SUBMITCOMMAND
title: "_D3DKMT_SUBMITCOMMAND"
author: windows-driver-content
description: The D3DKMT_SUBMITCOMMAND structure is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.
old-location: display\d3dkmt_submitcommand.htm
old-project: display
ms.assetid: FA6EA2BA-938C-4377-A85A-2168C4C1F3C6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_SUBMITCOMMAND, d3dkmthk/D3DKMT_SUBMITCOMMAND, _D3DKMT_SUBMITCOMMAND, D3DKMT_SUBMITCOMMAND structure [Display Devices], display.d3dkmt_submitcommand
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_SUBMITCOMMAND
product: Windows
targetos: Windows
req.typenames: D3DKMT_SUBMITCOMMAND
---

# _D3DKMT_SUBMITCOMMAND structure


## -description


The <b>D3DKMT_SUBMITCOMMAND</b> structure is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.


## -syntax


````
typedef struct _D3DKMT_SUBMITCOMMAND {
  D3DGPU_VIRTUAL_ADDRESS    Commands;
  UINT                      CommandLength;
  D3DKMT_SUBMITCOMMANDFLAGS Flags;
  ULONGLONG                 PresentHistoryToken;
  UINT                      BroadcastContextCount;
  D3DKMT_HANDLE             BroadcastContext[D3DDDI_MAX_BROADCAST_CONTEXT];
  VOID                      *pPrivateDriverData;
  UINT                      PrivateDriverDataSize;
  UINT                      NumPrimaries;
  D3DKMT_HANDLE             WrittenPrimaries[D3DDDI_MAX_WRITTEN_PRIMARIES];
  UINT                      NumHistoryBuffers;
  D3DKMT_HANDLE             *HistoryBufferArray;
} D3DKMT_SUBMITCOMMAND;
````


## -struct-fields




### -field Commands

The GPU virtual address for the commands being submitted to the context for execution. This information is provided to the driver during command submission and is also used for debugging purposes.


### -field CommandLength

Specifies the length, in bytes, of the commands being submitted to the GPU. 


### -field Flags

An instance of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_submitcommandflags.md">D3DDDICB_SUBMITCOMMANDFLAGS</a> structure.


### -field PresentHistoryToken

This member is reserved for future use.


### -field BroadcastContextCount

Specifies the number of context these command should be submitted to. This count must be at least 1.


### -field BroadcastContext

Specifies the handle of the context to execute the specified commands.


### -field pPrivateDriverData

Pointer to the driver private data to submitted by the user mode driver.


### -field PrivateDriverDataSize

Size of the private driver data information being passed. This size must be smaller than the size requested by the kernel mode  driver for submission private driver data or the call will fail.


### -field NumPrimaries

Specifies the number of primaries and swapchain back buffers being written to by the submitted commands. This is equal to the number of allocations in the <b>WrittenPrimaries</b> array.


### -field WrittenPrimaries

Arrays of handle to the primaries and swapchain back buffers being written to by the submitted commands.


### -field NumHistoryBuffers

This member is reserved for future use.


### -field HistoryBufferArray

This member is reserved for future use.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_submitcommandflags.md">D3DDDICB_SUBMITCOMMANDFLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SUBMITCOMMAND structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

