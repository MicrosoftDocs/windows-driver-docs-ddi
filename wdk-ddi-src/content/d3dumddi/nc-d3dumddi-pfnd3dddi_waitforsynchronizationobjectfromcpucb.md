---
UID: NC:d3dumddi.PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB
title: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB
author: windows-driver-content
description: pfnWaitForSynchronizationObjectFromCpuCb waits for a monitored fence to reach a certain value before processing subsequent context commands.
old-location: display\pfnwaitforsynchronizationobjectfromcpucb.htm
old-project: display
ms.assetid: 304A5BCE-19E6-4F92-B840-FD3BE1CFB856
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnwaitforsynchronizationobjectfromcpucb, pfnWaitForSynchronizationObjectFromCpuCb callback function [Display Devices], pfnWaitForSynchronizationObjectFromCpuCb, PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB, PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB, d3dumddi/pfnWaitForSynchronizationObjectFromCpuCb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	pfnWaitForSynchronizationObjectFromCpuCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB callback


## -description


<b>pfnWaitForSynchronizationObjectFromCpuCb</b> waits for a monitored fence to reach a certain value before processing subsequent context commands.


## -prototype


````
PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB pfnWaitForSynchronizationObjectFromCpuCb;

HRESULT APIENTRY CALLBACK* pfnWaitForSynchronizationObjectFromCpuCb(
         HANDLE                                      hDevice,
   const D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU *pData
)
{ ... }
````


## -parameters




### -param hDevice

A handle to the display device.


### -param *








#### - pData

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddicb_signalsynchronizationobjectfromcpu.md">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU</a> structure that provides the details of the requested operation.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



