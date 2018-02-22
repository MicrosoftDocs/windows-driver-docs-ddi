---
UID: NF:wiautil.wiauPropInPropSpec
title: wiauPropInPropSpec function
author: windows-driver-content
description: The wiauPropInPropSpec function determines whether a specified property specification ID is contained in an array of such values. The function optionally gets the index at which the property specification ID was found.
old-location: image\wiaupropinpropspec.htm
old-project: Image
ms.assetid: 5ab82378-ff12-46cc-814b-dc533db15a37
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: wiauPropInPropSpec, wiauPropInPropSpec function [Imaging Devices], wiautil/wiauPropInPropSpec, wiauFncs_8f694518-d3a5-4636-aae5-046ae519ce0e.xml, image.wiaupropinpropspec
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wiautil.h
apiname:
-	wiauPropInPropSpec
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# wiauPropInPropSpec function


## -description


The <b>wiauPropInPropSpec</b> function determines whether a specified property specification ID is contained in an array of such values. The function optionally gets the index at which the property specification ID was found.


## -syntax


````
BOOL _stdcall wiauPropInPropSpec(
                  LONG     NumPropSpecs,
  _In_      const PROPSPEC *pPropSpecs,
                  PROPID   PropId,
  _Out_opt_       int pIdx *pIdx = NULL
);
````


## -parameters




### -param NumPropSpecs

Specifies the number of property specification IDs in the array pointed to by <i>pPropSpecs</i>.


### -param pPropSpecs [in]

Points to the first element of the property specification ID array.


### -param PropId

Specifies the property specification ID to search for in the array pointed to by <i>pPropSpecs</i>.


### -param pIdx

TBD




#### - pIdx = NULL [out, optional]

<i>Optional</i>. Pointer to a memory location that receives the index of the property specification ID in the property specification ID array. The default value of this parameter is <b>NULL</b>, in which case the function does not use it.


## -returns



This function returns <b>TRUE</b> if it found the property specification ID in the property specification ID array. Otherwise it returns <b>FALSE</b>.




## -remarks



The <b>wiauPropInPropSpec</b> function finds a single property specification ID within an array of property specification IDs. A related function, <a href="..\wiautil\nf-wiautil-wiaupropsinpropspec.md">wiauPropsInPropSpec</a> can be used to determine whether any of a specified list of property specification IDs is found in another array of property specification IDs.




## -see-also

<a href="..\wiautil\nf-wiautil-wiaupropsinpropspec.md">wiauPropsInPropSpec</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20wiauPropInPropSpec function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

