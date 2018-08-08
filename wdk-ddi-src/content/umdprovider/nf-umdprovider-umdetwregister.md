---
UID: NF:umdprovider.UMDEtwRegister
title: UMDEtwRegister function
author: windows-driver-content
description: Registers the event trace provider. The driver should call this function before it makes any calls to log events.
old-location: display\umdetwregister.htm
tech.root: display
ms.assetid: 03352d5d-122f-4818-965d-f5cc8231d6ed
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: UMDEtwRegister, UMDEtwRegister function [Display Devices], display.umdetwregister, umdprovider/UMDEtwRegister
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: umdprovider.h
req.include-header: Umdprovider.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	HeaderDef
api_location:
-	umdprovider.h
api_name:
-	UMDEtwRegister
product:
- Windows
targetos: Windows
req.typenames: 
---

# UMDEtwRegister function


## -description


Registers the event trace provider. The driver should call this function before it makes any calls to log events.


## -parameters




### -param CbRundown

A pointer to a callback function that returns information about the current state of the user-mode driver.

This callback function should call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj542437">UMDEtwLogMapAllocation</a> function for every current allocation mapping.


## -returns



This function does not return a value.




## -remarks



The data type for the <i>CbRundown</i> parameter is defined as:

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef void (*PFNUMDETW_RUNDOWN)();</pre>
</td>
</tr>
</table></span></div>
<b>UMDEtwRegister</b> is defined inline in Umdprovider.h as:

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>// GUID for UMD ETW provider
// {A688EE40-D8D9-4736-B6F9-6B74935BA3B1}
static const GUID UMDEtwProviderId = 
{ 0xa688ee40, 0xd8d9, 0x4736, { 0xb6, 0xf9, 0x6b, 0x74, 0x93, 0x5b, 0xa3, 0xb1 } };

// Registration handle, returned by EventRegister and passed to EventUnregister
__declspec(selectany) REGHANDLE RegHandle = NULL;

// Whether any level of logging is enabled.
__declspec(selectany) BOOLEAN Enabled = FALSE;

// Whether we are currently in a rundown
__declspec(selectany) BOOLEAN InRundown = FALSE;

// Callback to the driver when a rundown is needed
__declspec(selectany) PFNUMDETW_RUNDOWN Rundown = NULL;

FORCEINLINE void NTAPI EnableCallback(
  __in      LPCGUID SourceId,
  __in      ULONG IsEnabled,
  __in      UCHAR Level,
  __in      ULONGLONG MatchAnyKeyword,
  __in      ULONGLONG MatchAllKeywords,
  __in_opt  PEVENT_FILTER_DESCRIPTOR FilterData,
  __in_opt  PVOID CallbackContext
)
{
    switch (IsEnabled)
    {
        case EVENT_CONTROL_CODE_DISABLE_PROVIDER:
            Enabled = FALSE;
            break;
        case EVENT_CONTROL_CODE_ENABLE_PROVIDER:
            Enabled = TRUE;
            break;
        case EVENT_CONTROL_CODE_CAPTURE_STATE:
            // Temporarily enable logging during the rundown
            BOOLEAN OldEnabled = Enabled;
            Enabled = TRUE;
            
            InRundown = TRUE;
            Rundown();
            InRundown = FALSE;

            // Restore Enabled to its original state
            Enabled = OldEnabled;
            
            break;
    }
}

FORCEINLINE void UMDEtwRegister(PFNUMDETW_RUNDOWN RundownCb)
{
    Rundown = RundownCb;

    // Register the provider
    EventRegister(&amp;UMDEtwProviderId,
                  EnableCallback,
                  NULL,
                  &amp;RegHandle);
}</pre>
</td>
</tr>
</table></span></div>
The <a href="https://msdn.microsoft.com/6025c3a6-7d88-49dc-bbc3-655c172dde3c">EventRegister</a> function and the <b>EVENT_CONTROL_CODE_XXX</b> values are  described in the <a href="https://msdn.microsoft.com/c10baa8d-50b9-4fda-89d0-d00b1d9f5404">Windows Events</a> documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj542437">UMDEtwLogMapAllocation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj542440">UMDEtwUnregister</a>
 

 

