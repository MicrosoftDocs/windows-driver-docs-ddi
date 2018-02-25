---
UID: NC:d3d12umddi.PFND3D12DDI_RESOURCEBARRIER_0022
title: PFND3D12DDI_RESOURCEBARRIER_0022
author: windows-driver-content
description: The pfnResourceBarrier callback function supports resource barriers.
old-location: display\pfnd3d12ddi_resourcebarrier_0022.htm
old-project: display
ms.assetid: AD42B7FC-9928-4386-B3EB-C9F0302415DA
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFND3D12DDI_RESOURCEBARRIER_0022, d3d12umddi/pfnResourceBarrier, display.pfnd3d12ddi_resourcebarrier_0022, pfnResourceBarrier, pfnResourceBarrier callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
-	UserDefined
apilocation:
-	D3d12umddi.h
apiname:
-	pfnResourceBarrier
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_RESOURCEBARRIER_0022 callback


## -description


The <i>pfnResourceBarrier</i> callback function supports resource barriers. 


## -prototype


````
PFND3D12DDI_RESOURCEBARRIER_0022 pfnResourceBarrier;

VOID APIENTRY* pfnResourceBarrier(
             D3D12DDI_HCOMMANDLIST                            hDrvCommandList,
             UINT                                             Count,
  _In_ const _reads_(Count) D3D12DDIARG_RESOURCE_BARRIER_0022 *ResourceBarrier
)
{ ... }
````


## -parameters




### -param D3D12DDI_HCOMMANDLIST


### -param Count

Specifies a count.


### -param *








#### - hDrvCommandList

The handle of a command list.


#### - ResourceBarrier [in]

A pointer to a resource barrier as a <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddiarg_resource_barrier_0022.md">D3D12DDIARG_RESOURCE_BARRIER_0022</a> structure. 


## -returns



This callback function does not return a value.




## -remarks



Access this callback function by using a command list functions structure, such as the <b>D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_0020</b> structure. 




## -see-also

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddiarg_resource_barrier_0022.md">D3D12DDIARG_RESOURCE_BARRIER_0022</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D12DDI_RESOURCEBARRIER_0022 callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

