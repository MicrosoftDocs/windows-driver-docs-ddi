---
UID: NF:wdtf.IWDTFDeviceDepot2.get_RootDevice
title: IWDTFDeviceDepot2::get_RootDevice method
author: windows-driver-content
description: Gets the root device.
old-location: dtf\iwdtfdevicedepot2_rootdevice.htm
old-project: dtf
ms.assetid: c0d055fb-16d0-41d4-a4d7-af7505f3f7d8
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdtf/IWDTFDeviceDepot2::get_RootDevice, Microsoft.WDTF.IWDTFDeviceDepot2.RootDevice, RootDevice property [Windows Device Testing Framework], IWDTFDeviceDepot2 interface, Microsoft::WDTF::IWDTFDeviceDepot2::RootDevice, get_RootDevice, dtf.iwdtfdevicedepot2_rootdevice, RootDevice property [Windows Device Testing Framework], wdtf/IWDTFDeviceDepot2::RootDevice, IWDTFDeviceDepot2, IWDTFDeviceDepot2.RootDevice, IWDTFDeviceDepot2::get_RootDevice, IWDTFDeviceDepot2 interface [Windows Device Testing Framework], RootDevice property
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTF.Interop.metadata_dll.dll
apiname:
-	IWDTFDeviceDepot2.RootDevice
-	IWDTFDeviceDepot2.get_RootDevice
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFDeviceDepot2::get_RootDevice method


## -description


Gets the root device.

This property is read-only.


## -syntax


````
HRESULT get_RootDevice(
  [out, retval] IWDTFTarget2 **pVal
);
````


## -parameters


## -see-also

<a href="..\wdtf\nn-wdtf-iwdtfdevicedepot2.md">IWDTFDeviceDepot2</a>



<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDeviceDepot2::RootDevice property%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

