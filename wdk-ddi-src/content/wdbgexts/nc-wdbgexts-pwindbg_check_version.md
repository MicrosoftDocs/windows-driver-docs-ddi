---
UID: NC:wdbgexts.PWINDBG_CHECK_VERSION
title: PWINDBG_CHECK_VERSION
description: The PWINDBG_CHECK_VERSION (CheckVersion) callback function verifies that the extension module version matches the debugger version, and outputs an warning message if there is a mismatch.
old-location: debugger\checkversion.htm
tech.root: debugger
ms.assetid: 82e16423-7e23-4229-9ba6-b43970a1135a
ms.date: 05/03/2018
ms.keywords: CheckVersion, CheckVersion callback function [Windows Debugging], PWINDBG_CHECK_VERSION, PWINDBG_CHECK_VERSION callback, WdbgExts_Callbacks_9f917023-190d-4047-a272-7e46de9b5afb.xml, debugger.checkversion, wdbgexts/CheckVersion
ms.topic: callback
req.header: wdbgexts.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdbgexts.h
api_name:
-	CheckVersion
product:
- Windows
targetos: Windows
req.typenames: 
---

# PWINDBG_CHECK_VERSION callback function


## -description


The <i>PWINDBG_CHECK_VERSION</i>  (<b>CheckVersion</b>) callback function verifies that the extension module version matches the debugger version, and outputs an warning message if there is a mismatch.


## -parameters












## -returns



None

<h2><a id="ddk_checkversion_dbwx"></a><a id="DDK_CHECKVERSION_DBWX"></a></h2>
<h3><a id="additional_information"></a><a id="ADDITIONAL_INFORMATION"></a>Additional Information</h3>
You must define this function in your code using the prototype above.

For more details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560220">Using WdbgExts Extension Callbacks</a>.




## -remarks



<i>CheckVersion</i> is an optional callback function.  If it exists, it will be called by the debugger the first time an extension function exported by the extension DLL is used.

The purpose of this function is to allow you to print out a version mismatch warning when the extension DLL is used. This is an optional feature, which should not be confused with the version number used  by <a href="https://msdn.microsoft.com/library/windows/hardware/ff543968">ExtensionApiVersion</a>.

If the <a href="https://msdn.microsoft.com/ce7fbff4-7936-4bef-8236-a13957ada7f4">.noversion</a> command is used, version checking is disabled and the debugger will not call <i>CheckVersion</i>.



