---
UID: NF:wdm.EtwWriteString
title: EtwWriteString function
author: windows-driver-content
description: The EventWriteString function is a tracing function that you can use when no sophisticated data is required. This function is similar to a debug print statement.
old-location: devtest\etwwritestring.htm
tech.root: devtest
ms.assetid: 25de7729-f43f-4d16-a379-e1cb1ab8616c
ms.date: 02/23/2018
ms.keywords: EtwWriteString, EtwWriteString function [Driver Development Tools], devtest.etwwritestring, etw_km_b4cb697f-3523-4730-8df5-1faf201af7f8.xml, wdm/EtwWriteString
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (See Comments section.)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	EtwWriteString
product:
- Windows
targetos: Windows
req.typenames: 
---

# EtwWriteString function


## -description


The <b>EventWriteString</b> function is a tracing function that you can use when no sophisticated data is required. This function is similar to a debug print statement. 


## -parameters




### -param RegHandle [in]

A Pointer to the event provider registration handle, which is returned by the <b>EtwRegister</b> function if the event provider registration is successful.


### -param Level [in]

The level at which the event is active.  


### -param Keyword [in]

The keyword for the event. A keyword is a bitmask that makes general statements about the category of the event or error. Because the keyword is a bitmask, you can apply more than one keyword to a single event. You can define the keywords and bit positions, or you can use Windows-standard keywords, or you can use combination of your own keywords and the Windows keywords.


### -param ActivityId [in, optional]

The identifier that indicates the activity associated with the event. The <i>ActivityId</i> provides a way to group related events and is used in end-to-end tracing. This identifier is optional and can be <b>NULL</b>.


### -param String [in]

A null-terminated string (WCHAR). 


## -returns



The function returns STATUS_SUCCESS if the event is published successfully.




## -remarks



Because the string produced by <b>EventWriteString</b> function is not localizable, this function is not recommended for use in production code. This function should not be used to log highly visible events.

You can call <b>EtwWriteString</b> at any IRQL. However, when IRQL is greater than APC_LEVEL, any data passed to the <b>EtwWrite</b>, <a href="https://msdn.microsoft.com/library/windows/hardware/dn144773">EtwWriteEx</a>, <b>EtwWriteString</b>,  and <b>EtwWriteTransfer</b> functions must not be pageable. That is, any kernel-mode routine that is running at IRQL greater than APC_LEVEL cannot access pageable memory. Data passed to the <b>EtwWrite</b>, <b>EtwWriteEx</b>, <b>EtwWriteString</b>, and <b>EtwWriteTransfer</b> functions must reside in system-space memory, regardless of what the IRQL is.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545627">EtwWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn144773">EtwWriteEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545642">EtwWriteTransfer</a>
 

 

