---
UID: NF:printerextension.IPrinterQueue2.SendBidiSetRequestAsync
title: IPrinterQueue2::SendBidiSetRequestAsync
author: windows-driver-content
description: Uses an XML string value to send a Bidi Set request as an asynchronous operation.
old-location: print\iprinterqueue2_sendbidisetrequestasync.htm
tech.root: print
ms.assetid: 05FF8A47-A586-4DA7-94AD-A7186265ADB4
ms.date: 4/20/2018
ms.keywords: IPrinterQueue2 interface [Print Devices],SendBidiSetRequestAsync method, IPrinterQueue2.SendBidiSetRequestAsync, IPrinterQueue2::SendBidiSetRequestAsync, SendBidiSetRequestAsync, SendBidiSetRequestAsync method [Print Devices], SendBidiSetRequestAsync method [Print Devices],IPrinterQueue2 interface, print.iprinterqueue2_sendbidisetrequestasync, printerextension/IPrinterQueue2::SendBidiSetRequestAsync
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterQueue2.SendBidiSetRequestAsync
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterQueue2::SendBidiSetRequestAsync


## -description


Uses an XML string value to send a Bidi Set request as an asynchronous operation.

This method allows the user to perform device maintenance tasks from within a UWP device app  for printers.


## -parameters




### -param bstrBidiRequest [in]

XML string that is used to transfer the data for the  Set request.


### -param pCallback [in]

Callback object for the Bidi Set request.


### -param ppAsyncOperation [out, retval]

Context object associated with the asynchronous Bidi Set  request (operation).


## -returns



This method returns the appropriate <b>HRESULT</b> value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265385">IPrinterBidiSetRequestCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265387">IPrinterExtensionAsyncOperation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265389">IPrinterQueue2</a>
 

 

