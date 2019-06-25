---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvInitializeWia
title: IWiaMiniDrv::drvInitializeWia (wiamindr_lh.h)
description: The IWiaMiniDrv::drvInitializeWia method initializes the minidriver and builds the driver item tree representing the device.
old-location: image\iwiaminidrv_drvinitializewia.htm
tech.root: image
ms.assetid: 93b155eb-0254-441f-b01f-3da8eb7376a5
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvInitializeWia method, IWiaMiniDrv.drvInitializeWia, IWiaMiniDrv::drvInitializeWia, MiniDrv_04485b20-ff45-4cf7-a861-841bf03befcf.xml, drvInitializeWia, drvInitializeWia method [Imaging Devices], drvInitializeWia method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvinitializewia, wiamindr_lh/IWiaMiniDrv::drvInitializeWia
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
- IWiaMiniDrv.drvInitializeWia
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv::drvInitializeWia


## -description


The <b>IWiaMiniDrv::drvInitializeWia</b> method initializes the minidriver and builds the driver item tree representing the device.


## -parameters




### -param __MIDL__IWiaMiniDrv0000




### -param __MIDL__IWiaMiniDrv0001




### -param __MIDL__IWiaMiniDrv0002




### -param __MIDL__IWiaMiniDrv0003




### -param __MIDL__IWiaMiniDrv0004




### -param __MIDL__IWiaMiniDrv0005




### -param __MIDL__IWiaMiniDrv0006




### -param __MIDL__IWiaMiniDrv0007




### -param __MIDL__IWiaMiniDrv0008






#### - bstrDeviceID [in]

Specifies a string containing the device's unique identifier.


#### - bstrRootFullItemName [in]

Specifies a string containing the full name of the root item.


#### - lFlags [in]

Is reserved. Set to zero.


#### - pIUnknownOuter [in, optional]

(Optional) Points to a memory location that can receive the address of an <b>IUnknown</b> interface. 


#### - pStiDevice [in, optional]

Points to an <a href="https://docs.microsoft.com/windows-hardware/drivers/image/istidevice-com-interface">IStiDevice COM Interface</a>.


#### - pWiasContext [in]

Pointer to a WIA item context.


#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.


#### - ppIDrvItemRoot [out, optional]

Points to a memory location that will receive the address of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiadrvitem">IWiaDrvItem Interface</a>, the interface of the root item.


#### - ppIUnknownInner [out, optional]

(Optional) Points to a memory location that can receive the address of an <b>IUnknown</b> interface. If the minidriver has functionality that is not accessible through the <b>IWiaMiniDrv</b> interface, the vendor can create a separate interface on the minidriver. This parameter provides access to that functionality.


## -returns



On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by <i>plDevErrVal</i>.

The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr">IWiaMiniDrv::drvGetDeviceErrorStr</a>.




## -remarks



This method should initialize any private structures and create the driver item tree. For detailed information about the steps that minidrivers typically perform in this method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/image/initializing-the-wia-minidriver">Initializing the WIA Minidriver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/image/creating-the-wia-driver-item-tree">Creating the WIA Driver Item Tree</a>.

The WIA service calls the <b>IWiaMiniDrv::drvInitializeWia</b> method in response to a client's call to the <b>CreateDevice</b> function (described in the Microsoft Windows SDK documentation), which means that this method is called once for each new client connection.

For example, if the user right-clicks a WIA scanner icon in <b>My Computer</b>, the shell calls <b>CreateDevice</b>, which generates a call to the minidriver's <b>IWiaMiniDrv::drvInitializeWia</b> method. If the user then runs the WIA <b>Acquisition Wizard</b>, it also calls <b>CreateDevice</b>. Each time that <b>CreateDevice</b> is called, there is a corresponding call to the <b>IWiaMiniDrv::drvInitializeWia</b> method on the minidriver.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-additemtofolder">IWiaDrvItem::AddItemToFolder</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv">IWiaMiniDrv</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr">IWiaMiniDrv::drvGetDeviceErrorStr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvuninitializewia">IWiaMiniDrv::drvUnInitializeWia</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiascreatedrvitem">wiasCreateDrvItem</a>
 

 

