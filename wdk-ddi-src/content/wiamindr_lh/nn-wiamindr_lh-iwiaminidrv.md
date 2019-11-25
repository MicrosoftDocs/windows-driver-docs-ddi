---
UID: NN:wiamindr_lh.IWiaMiniDrv
title: IWiaMiniDrv (wiamindr_lh.h)
description: The IWiaMiniDrv interface provides the methods that are the entry points for all communication between the minidriver and the WIA service. These methods allow the WIA service to control the device.
old-location: image\iwiaminidrv_interface.htm
tech.root: image
ms.assetid: 15068d10-5e24-427c-9684-24ce67b75ada
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrv, IWiaMiniDrv interface [Imaging Devices], IWiaMiniDrv interface [Imaging Devices],described, MiniDrv_8a22bfee-13f8-4efc-b31d-8dd9fabfe131.xml, image.iwiaminidrv_interface, wiamindr_lh/IWiaMiniDrv
ms.topic: interface
f1_keywords:
 - "wiamindr_lh/IWiaMiniDrv"
req.header: wiamindr_lh.h
req.include-header: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wiamindr_lh.h
api_name:
- IWiaMiniDrv
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv interface

## -description

The **IWiaMiniDrv** interface provides the methods that are the entry points for all communication between the minidriver and the WIA service. These methods allow the WIA service to control the device.

A WIA minidriver writer must implement each method in this interface, although the implementations are not required to do anything more than return E_NOTIMPL (for [IWiaMiniDrv::drvAnalyzeItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvanalyzeitem) and [IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr)) or S_OK (for the other methods in this interface).

## -inheritance

