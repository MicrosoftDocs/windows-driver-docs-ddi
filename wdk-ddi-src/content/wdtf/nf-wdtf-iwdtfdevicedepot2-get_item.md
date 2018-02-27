---
UID: NF:wdtf.IWDTFDeviceDepot2.get_Item
title: IWDTFDeviceDepot2::get_Item method
author: windows-driver-content
description: Gets an individual device in the DeviceDepot.
old-location: dtf\iwdtfdevicedepot2_item.htm
old-project: dtf
ms.assetid: 9411437c-60d8-424e-b54c-7750f1c4dd9e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFDeviceDepot2, IWDTFDeviceDepot2 interface [Windows Device Testing Framework], Item property, IWDTFDeviceDepot2.Item, IWDTFDeviceDepot2::get_Item, Item property [Windows Device Testing Framework], Item property [Windows Device Testing Framework], IWDTFDeviceDepot2 interface, Microsoft.WDTF.IWDTFDeviceDepot2.Item, Microsoft::WDTF::IWDTFDeviceDepot2::Item, dtf.iwdtfdevicedepot2_item, get_Item,IWDTFDeviceDepot2.get_Item, wdtf/IWDTFDeviceDepot2::Item, wdtf/IWDTFDeviceDepot2::get_Item
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
req.type-library: 
req.lib: wdtf.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTFDeviceDepot2.Item
-	IWDTFDeviceDepot2.get_Item
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFDeviceDepot2::get_Item method


## -description


Gets an individual device in the DeviceDepot.

This property is read-only.


## -syntax


````
HRESULT get_Item(
  [in]          LONG         Index,
  [out, retval] IWDTFTarget2 **ppTarget
);
````


## -parameters


## -see-also

<a href="..\wdtf\nn-wdtf-iwdtfdevicedepot2.md">IWDTFDeviceDepot2</a>



<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDeviceDepot2::Item property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

