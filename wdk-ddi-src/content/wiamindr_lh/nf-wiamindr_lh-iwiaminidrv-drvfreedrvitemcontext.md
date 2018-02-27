---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvFreeDrvItemContext
title: IWiaMiniDrv::drvFreeDrvItemContext method
author: windows-driver-content
description: The IWiaMiniDrv::drvFreeDrvItemContext method frees a device-specific context.
old-location: image\iwiaminidrv_drvfreedrvitemcontext.htm
old-project: image
ms.assetid: bc4f751f-d92a-47e6-8cbe-0a587292b160
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWiaMiniDrv, IWiaMiniDrv interface [Imaging Devices], drvFreeDrvItemContext method, IWiaMiniDrv::drvFreeDrvItemContext, MiniDrv_59a7d220-cd1d-4cc2-870a-3260feaba7e9.xml, drvFreeDrvItemContext method [Imaging Devices], drvFreeDrvItemContext method [Imaging Devices], IWiaMiniDrv interface, drvFreeDrvItemContext,IWiaMiniDrv.drvFreeDrvItemContext, image.iwiaminidrv_drvfreedrvitemcontext, wiamindr_lh/IWiaMiniDrv::drvFreeDrvItemContext
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: wiamindr_lh.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	wiamindr_lh.h
api_name:
-	IWiaMiniDrv.drvFreeDrvItemContext
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---

# IWiaMiniDrv::drvFreeDrvItemContext method


## -description


The <b>IWiaMiniDrv::drvFreeDrvItemContext</b> method frees a device-specific context.


## -syntax


````
HRESULT drvFreeDrvItemContext(
  [in]  LONG lFlags,
  [in]  BYTE *pSpecContext,
  [out] LONG *plDevErrVal
);
````


## -parameters




### -param __MIDL__IWiaMiniDrv0056




### -param __MIDL__IWiaMiniDrv0057




### -param __MIDL__IWiaMiniDrv0058






#### - lFlags [in]

Is currently unused.


#### - pSpecContext [in]

Points to a device-specific context. 


#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.


## -returns



On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If the method fails, it should return a standard COM error code and place a minidriver-specific error code in the memory pointed to by <i>plDevErrVal</i>. 

The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>.






## -remarks



When a driver item is deleted, the WIA service frees the driver item context. This method informs the minidriver that the context is ready to be freed. The minidriver should free any memory that it allocated for the context. For example, in <a href="https://msdn.microsoft.com/library/windows/hardware/ff545005">IWiaMiniDrv::drvReadItemProperties</a>, a camera minidriver might allocate a cache to store the thumbnail for an item, and store a pointer to this cache in the driver item context. The minidriver would then free the cache in this method.




## -see-also

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrv.md">IWiaMiniDrv</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545005">IWiaMiniDrv::drvReadItemProperties</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrv::drvFreeDrvItemContext method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

