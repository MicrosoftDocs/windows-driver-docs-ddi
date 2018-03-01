---
UID: NF:wdtf.IWDTFTarget2.get_Type
title: IWDTFTarget2::get_Type method
author: windows-driver-content
description: Gets a value that identifies the depot that the target comes from.
old-location: dtf\iwdtftarget2_type.htm
old-project: dtf
ms.assetid: 76b13505-7404-475c-98d8-fe3b3ed25720
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFTarget2, IWDTFTarget2 interface [Windows Device Testing Framework], Type property, IWDTFTarget2.Type, IWDTFTarget2::get_Type, Microsoft.WDTF.IWDTFTarget2.Type, Microsoft::WDTF::IWDTFTarget2::Type, Type property [Windows Device Testing Framework], Type property [Windows Device Testing Framework], IWDTFTarget2 interface, dtf.iwdtftarget2_type, get_Type,IWDTFTarget2.get_Type, wdtf/IWDTFTarget2::Type, wdtf/IWDTFTarget2::get_Type
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
-	IWDTFTarget2.Type
-	IWDTFTarget2.get_Type
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFTarget2::get_Type method


## -description


Gets a value that identifies the depot that the target comes from.

This property is read-only.


## -syntax


````
HRESULT get_Type(
  [out, retval] BSTR *pVal
);
````


## -parameters


## -remarks



The value can be one of the following:

<ul>
<li>
<b>Device</b> if the target comes from the 
<a href="..\wdtf\nn-wdtf-iwdtfdevicedepot2.md">IWDTFDeviceDepot2</a> interface.

</li>
<li>
<b>System</b> if the target comes from the 
<a href="..\wdtf\nn-wdtf-iwdtfsystemdepot2.md">IWDTFSystemDepot2</a> interface.

</li>
</ul>



## -see-also

<a href="..\wdtf\nn-wdtf-iwdtfsystemdepot2.md">IWDTFSystemDepot2</a>



<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>



<a href="..\wdtf\nn-wdtf-iwdtfdevicedepot2.md">IWDTFDeviceDepot2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFTarget2::Type property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

