---
UID: NF:iddcx.IddCxAdapterInitAsync
title: IddCxAdapterInitAsync function
author: windows-driver-content
description: An asynchronous initiation function called by the driver to create a WDDM graphics adapter.
old-location: display\iddcxadapterinitasync.htm
tech.root: display
ms.assetid: c23d0d24-b043-4e39-afd3-abab6bb84769
ms.date: 05/10/2018
ms.keywords: IddCxAdapterInitAsync, IddCxAdapterInitAsync method [Display Devices], display.iddcxadapterinitasync, iddcx/IddCxAdapterInitAsync
ms.topic: function
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
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
req.lib: IddCxStub.lib 
req.dll: IddCx.dll 
req.irql: "_Must_inspect_result_"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	IddCx.dll
api_name:
-	IddCxAdapterInitAsync
product:
- Windows
targetos: Windows
req.typenames: 
---

# IddCxAdapterInitAsync function


## -description


An asynchronous initiation function called by the driver to create a WDDM graphics adapter.

                


## -parameters




### -param pInArgs [in]

Input arguments to the function


### -param pOutArgs [out]

Output arguments to the function


## -returns




(NTSTATUS) The method returns S_OK if the operation succeeds. Otherwise, this method returns an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    



