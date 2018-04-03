---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.RescanParentDevice
title: IWDTFPNPAction2::RescanParentDevice method
author: windows-driver-content
description: Rescans and re-enumerates the target device's parent device.
old-location: dtf\iwdtfpnpaction2_rescanparentdevice.htm
old-project: dtf
ms.assetid: 5b25cffa-df53-49d5-be26-1901eddfdad2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFPNPAction2, IWDTFPNPAction2 interface [Windows Device Testing Framework], RescanParentDevice method, IWDTFPNPAction2::RescanParentDevice, Microsoft.WDTF.IWDTFPNPAction2.RescanParentDevice, Microsoft::WDTF::IWDTFPNPAction2::RescanParentDevice, RescanParentDevice method [Windows Device Testing Framework], RescanParentDevice method [Windows Device Testing Framework], IWDTFPNPAction2 interface, RescanParentDevice,IWDTFPNPAction2.RescanParentDevice, dtf.iwdtfpnpaction2_rescanparentdevice, wdtfpnpaction/IWDTFPNPAction2::RescanParentDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfpnpaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFPNPAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverPNPAction.Interop.dll
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFDriverPNPAction.Interop.dll
api_name:
-	IWDTFPNPAction2.RescanParentDevice
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFPNPAction2::RescanParentDevice method


## -description


Rescans and re-enumerates the target device's parent device.


## -parameters




### -param pbSuccess [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



In essence, <b>RescanParentDevice</b> calls 
<b>CM_Reenumerate_DevNode()</b>. See the MSDN documentation for 
<b>CM_Reenumerate_DevNode()</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451065">IWDTFPNPAction2</a>
 

 

