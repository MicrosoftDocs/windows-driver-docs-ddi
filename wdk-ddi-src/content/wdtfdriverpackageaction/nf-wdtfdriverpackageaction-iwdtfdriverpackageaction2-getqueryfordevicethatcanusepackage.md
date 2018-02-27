---
UID: NF:wdtfdriverpackageaction.IWDTFDriverPackageAction2.GetQueryForDeviceThatCanUsePackage
title: IWDTFDriverPackageAction2::GetQueryForDeviceThatCanUsePackage method
author: windows-driver-content
description: Returns an SDEL statement that queries for all devices that can use the driver package.
old-location: dtf\iwdtfdriverpackageaction2_getqueryfordevicethatcanusepackage.htm
old-project: dtf
ms.assetid: 218146e6-c94a-455a-ab87-1e77da3152f2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetQueryForDeviceThatCanUsePackage,IWDTFDriverPackageAction2.GetQueryForDeviceThatCanUsePackage, GetQueryForDevicesThatCanUsePackage method [Windows Device Testing Framework], GetQueryForDevicesThatCanUsePackage method [Windows Device Testing Framework], IWDTFDriverPackageAction2 interface, IWDTFDriverPackageAction2, IWDTFDriverPackageAction2 interface [Windows Device Testing Framework], GetQueryForDevicesThatCanUsePackage method, IWDTFDriverPackageAction2::GetQueryForDeviceThatCanUsePackage, IWDTFDriverPackageAction2::GetQueryForDevicesThatCanUsePackage, Microsoft.WDTF.IWDTFDriverPackageAction2.GetQueryForDevicesThatCanUsePackage, Microsoft::WDTF::IWDTFDriverPackageAction2::GetQueryForDevicesThatCanUsePackage, dtf.iwdtfdriverpackageaction2_getqueryfordevicethatcanusepackage, wdtfdriverpackageaction/IWDTFDriverPackageAction2::GetQueryForDevicesThatCanUsePackage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfdriverpackageaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFDriverPackageAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverPackageAction.Interop.dll
req.type-library: 
req.lib: wdtfdriverpackageaction.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFDriverPackageAction.Interop.dll
apiname:
-	IWDTFDriverPackageAction2.GetQueryForDevicesThatCanUsePackage
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFDriverPackageAction2::GetQueryForDeviceThatCanUsePackage method


## -description


Returns an SDEL statement that queries for all devices that can use the driver package.


## -syntax


````
HRESULT GetQueryForDevicesThatCanUsePackage(
  [out, retval] BSTR *pSDEL
);
````


## -parameters




### -param pSDEL [out, retval]

The SDEL statement.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfdriverpackageaction\nn-wdtfdriverpackageaction-iwdtfdriverpackageaction2.md">IWDTFDriverPackageAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDriverPackageAction2::GetQueryForDevicesThatCanUsePackage method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

