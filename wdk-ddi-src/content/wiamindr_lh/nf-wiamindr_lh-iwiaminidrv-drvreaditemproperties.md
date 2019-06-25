---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvReadItemProperties
title: IWiaMiniDrv::drvReadItemProperties (wiamindr_lh.h)
description: The IWiaMiniDrv::drvReadItemProperties method reads the driver item properties that need to be updated.
old-location: image\iwiaminidrv_drvreaditemproperties.htm
tech.root: image
ms.assetid: 015c2e02-62aa-4037-9974-c8e4b8784fe5
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvReadItemProperties method, IWiaMiniDrv.drvReadItemProperties, IWiaMiniDrv::drvReadItemProperties, MiniDrv_515d9cc7-c76a-4a15-9cc1-59be834382fe.xml, drvReadItemProperties, drvReadItemProperties method [Imaging Devices], drvReadItemProperties method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvreaditemproperties, wiamindr_lh/IWiaMiniDrv::drvReadItemProperties
ms.topic: method
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later.
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
- IWiaMiniDrv.drvReadItemProperties
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv::drvReadItemProperties


## -description


The <b>IWiaMiniDrv::drvReadItemProperties</b> method reads the driver item properties that need to be updated.


## -parameters




### -param __MIDL__IWiaMiniDrv0025




### -param __MIDL__IWiaMiniDrv0026




### -param __MIDL__IWiaMiniDrv0027




### -param __MIDL__IWiaMiniDrv0028




### -param __MIDL__IWiaMiniDrv0029






#### - lFlags [in]

Is reserved. Set to zero.


#### - nPropSpec [in]

Indicates the number of items in the <i>pPropSpec</i> array.


#### - pPropSpec [in]

Points to the first element of an array of PROPSPEC structures (defined in the Microsoft Windows SDK documentation). 


#### - pWiasContext [in]

Pointer to a WIA item context.


#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.


## -returns



On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by <i>plDevErrVal</i>. 

The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr">IWiaMiniDrv::drvGetDeviceErrorStr</a>.




## -remarks



In this method, the minidriver should read the requested properties from the device. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv">IWiaMiniDrv</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr">IWiaMiniDrv::drvGetDeviceErrorStr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvwriteitemproperties">IWiaMiniDrv::drvWriteItemProperties</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswritemultiple">wiasWriteMultiple</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswritepropbin">wiasWritePropBin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswritepropfloat">wiasWritePropFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswritepropguid">wiasWritePropGuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswriteproplong">wiasWritePropLong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswritepropstr">wiasWritePropStr</a>
 

 

