---
UID: NC:wdm.PCW_CALLBACK
title: PCW_CALLBACK
author: windows-driver-content
description: Providers can implement a PCW_CALLBACK function to receive notification when consumers perform certain actions, such as adding or removing counters from a query.
old-location: devtest\pcwcallback.htm
old-project: devtest
ms.assetid: 5058fc17-1016-45bc-a6ea-5e2458824e7b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PCW_CALLBACK, PcwCallback, PcwCallback callback function [Driver Development Tools], devtest.pcwcallback, km_pcw_f4d70925-0361-4aa6-9e4b-3f1e00a01535.xml, wdm/PcwCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: "<=APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	PcwCallback
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PCW_CALLBACK callback


## -description


Providers can implement a <i>PCW_CALLBACK</i> function to receive notification when consumers perform certain actions, such as adding or removing counters from a query. The Performance Counter Library (PERFLIB version 2.0) calls the <i>PCW_CALLBACK</i> function before the consumer's request completes.


## -prototype


````
PCW_CALLBACK PcwCallback;

NTSTATUS PcwCallback(
  _In_     PCW_CALLBACK_TYPE         Type,
  _In_     PPCW_CALLBACK_INFORMATION Info,
  _In_opt_ PVOID                     Context
)
{ ... }
````


## -parameters




### -param Type [in]

The callback type. Specifies why the callback is called. Possible values are PcwCallbackAddCounter, PcwCallbackRemoveCounter, PcwCallbackEnumerateInstances, and PcwCallbackCollectData. 


### -param Info [in]

A pointer to a PCW_CALLBACK_INFORMATION union that supplies details about the reason why the provider is being called.


### -param Context [in, optional]

A pointer to the callback context. This value is supplied by the provider when calling <a href="..\wdm\nf-wdm-pcwregister.md">PcwRegister</a>.


## -returns



The <i>PCW_CALLBACK</i> callback function must return STATUS_SUCCESS if the callback was successfully executed. Otherwise, this callback function must return STATUS_UNSUCCESSFUL.




## -remarks



Providers that do not want to, or are unable to, create and destroy instances can register a callback function that is called when data is requested. For example, the following code examples show how the provider can use the <i>PCW_CALLBACK</i> callback function to enumerate and collect data.

The following code, from KcsCounters.h shows the inline function <b>KcsRegisterGeometricWave</b> that Ctrpp.exe generates from the manifest for the KCS sample in the WDK, Kcs.man. This function registers the counter set and takes a parameter to an optional custom <i>Callback</i> function. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EXTERN_C FORCEINLINE NTSTATUS
KcsRegisterGeometricWave(
    __in_opt PPCW_CALLBACK Callback,
    __in_opt PVOID CallbackContext
    )
{
    PCW_REGISTRATION_INFORMATION RegInfo;
    UNICODE_STRING Name = RTL_CONSTANT_STRING(L"Geometric Waves");
    PCW_COUNTER_DESCRIPTOR Descriptors[] = {
 { 1, 0, FIELD_OFFSET(GEOMETRIC_WAVE_VALUES, Triangle), RTL_FIELD_SIZE(GEOMETRIC_WAVE_VALUES, Triangle)},
 { 2, 0, FIELD_OFFSET(GEOMETRIC_WAVE_VALUES, Square), RTL_FIELD_SIZE(GEOMETRIC_WAVE_VALUES, Square)},
    };

    PAGED_CODE();

 RtlZeroMemory(&amp;RegInfo, sizeof RegInfo);

 RegInfo.Version = PCW_CURRENT_VERSION;
 RegInfo.Counters = Descriptors;
 RegInfo.CounterCount = RTL_NUMBER_OF(Descriptors);
 RegInfo.Callback = Callback;
 RegInfo.CallbackContext = CallbackContext;
 RegInfo.Name = &amp;Name;

 return PcwRegister(&amp;KcsGeometricWave, &amp;RegInfo);
}</pre>
</td>
</tr>
</table></span></div>
The provider can implement the <i>Callback</i> function to handle the requests. The following code example shows a <i>PCW_CALLBACK</i> function that enumerates and collects data. The function is named <i>KcsGeometricWaveCallback</i>. This function is then passed to the <i>KcsRegisterGeometricWave</i> in the <i>Callback</i> parameter.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS NTAPI
KcsGeometricWaveCallback (
    __in PCW_CALLBACK_TYPE Type,
    __in PPCW_CALLBACK_INFORMATION Info,
    __in_opt PVOID Context
    )

/*++

Routine Description:
    This function returns the list of counter instances and counter data.
Arguments:
    Type - Request type.
    Info - Buffer for returned data.
 Context - Not used.
Return Value:
 NTSTATUS indicating if the function succeeded.

--*/

{
    NTSTATUS Status;
    UNICODE_STRING UnicodeName;

    UNREFERENCED_PARAMETER(Context);

    PAGED_CODE();

 switch (Type) {
 case PcwCallbackEnumerateInstances:

        //
        // Instances are being enumerated, so we add them without values.
        //

 RtlInitUnicodeString(&amp;UnicodeName, L"Small Wave");
        Status = KcsAddGeometricWave(Info-&gt;EnumerateInstances.Buffer,
                                     &amp;UnicodeName,
                                     0,
                                     NULL);
 if (!NT_SUCCESS(Status)) {
 return Status;
        }

 RtlInitUnicodeString(&amp;UnicodeName, L"Medium Wave");
        Status = KcsAddGeometricWave(Info-&gt;EnumerateInstances.Buffer,
                                     &amp;UnicodeName,
                                     0,
                                     NULL);
 if (!NT_SUCCESS(Status)) {
 return Status;
        }

 RtlInitUnicodeString(&amp;UnicodeName, L"Large Wave");
        Status = KcsAddGeometricWave(Info-&gt;EnumerateInstances.Buffer,
                                     &amp;UnicodeName,
                                     0,
                                     NULL);
 if (!NT_SUCCESS(Status)) {
 return Status;
        }

 break;

 case PcwCallbackCollectData:

        //
        // Add values for 3 instances of Geometric Wave Counter Set.
        //

        Status = KcsAddGeometricInstance(Info-&gt;CollectData.Buffer,
 L"Small Wave",
                                         40,
                                         20);
 if (!NT_SUCCESS(Status)) {
 return Status;
        }

        Status = KcsAddGeometricInstance(Info-&gt;CollectData.Buffer,
 L"Medium Wave",
                                         30,
                                         40);
 if (!NT_SUCCESS(Status)) {
 return Status;
        }

        Status = KcsAddGeometricInstance(Info-&gt;CollectData.Buffer,
 L"Large Wave",
                                         20,
                                         60);
 if (!NT_SUCCESS(Status)) {
 return Status;
        }

 break;
    }

 return STATUS_SUCCESS;
}</pre>
</td>
</tr>
</table></span></div>
In the <i>DriverEntry</i> routine of the KCS example, the <i>KcsGeometricWaveCallback</i> function is specified as the <i>Callback</i> when <i>KcsRegisterGeometricWave</i> registers the counter set. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>//
    // Register Countersets.
    //

    Status = KcsRegisterGeometricWave(KcsGeometricWaveCallback, NULL);
 if (!NT_SUCCESS(Status)) {
 return Status;
    }</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdm\nf-wdm-pcwregister.md">PcwRegister</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=144623">Performance Counter Library (PERFLIB)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20PCW_CALLBACK callback function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

