---
UID: NF:wudfddi.IWDFDevice3.MapIoSpace
title: IWDFDevice3::MapIoSpace (wudfddi.h)
description: The MapIoSpace method maps the given physical address range to system address space and returns a pseudo base address.
old-location: wdf\iwdfdevice3_mapiospace.htm
tech.root: wdf
ms.assetid: 243C7299-7C74-408A-8FB9-32FB3315251F
ms.date: 02/26/2018
ms.keywords: IWDFDevice3 interface,MapIoSpace method, IWDFDevice3.MapIoSpace, IWDFDevice3::\_MapIoSpace, IWDFDevice3::MapIoSpace, MapIoSpace, MapIoSpace method, MapIoSpace method,IWDFDevice3 interface, umdf.iwdfdevice3_mapiospace, wdf.iwdfdevice3_mapiospace, wudfddi/IWDFDevice3::\_MapIoSpace
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFDevice3.MapIoSpace
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice3::MapIoSpace


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>MapIoSpace</b> method maps the given physical address range to system address space and returns a pseudo base address. 


## -parameters




### -param PhysicalAddress [in]

Specifies the starting 64-bit physical address of the I/O range to be mapped.


### -param NumberOfBytes [in]

Specifies a value greater than zero, indicating the number of bytes to be mapped.


### -param CacheType [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a> value, which indicates the cache attribute to use to map the physical address range. The MEMORY_CACHING_TYPE enumeration type is defined in Wudfwdm.h.


### -param pPseudoBaseAddress [out]

The address of a location that receives a pointer to the pseudo base address.


## -returns



The method returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



A driver must call this method during device start-up if it receives translated resources of type <b>CmResourceTypeMemory</b> in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure. <b>MapIoSpace</b> maps the physical address returned in the resource list to a framework-managed address referred to as the pseudo base address.

 The driver can then use the pseudo base address to access device registers with READ_REGISTER_<i>Xxx</i> and WRITE_REGISTER_<i>Xxx</i> functions. For  an example, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reading-and-writing-to-device-registers-in-umdf-1-x-drivers">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.

A driver that calls <b>MapIoSpace</b> must set the <b>UmdfDirectHardwareAccess</b> INF directive to <b>AllowDirectHardwareAccess</b>.

 If the driver sets the <b>UmdfRegisterAccessMode</b> INF directive to <b>RegisterAccessUsingUserModeMapping</b>, calling <b>MapIoSpace</b> also maps the given physical address range to a user-mode base address range that the driver can subsequently access by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice3-gethardwareregistermappedaddress">GetHardwareRegisterMappedAddress</a>.

 For more information about  INF directives that UMDF drivers can use, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/specifying-wdf-directives-in-inf-files">Specifying WDF Directives in INF Files</a>.

The PHYSICAL_ADDRESS type is defined in Wudfwdm.h, as follows:<pre class="syntax" xml:space="preserve"><code>typedef LARGE_INTEGER PHYSICAL_ADDRESS;</code></pre>



#### Examples

In the following code example, a UMDF driver uses its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onpreparehardware">IPnpCallbackHardware2::OnPrepareHardware</a> callback function to examine its memory-mapped register resources and map them into user-mode address space. The example then implements  a <b>WriteToDevice</b> method that accesses the memory locations. The driver then calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice3-unmapiospace">UnmapIoSpace</a> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onreleasehardware">IPnpCallbackHardware2::OnReleaseHardware</a> callback. The driver’s INF file must enable UMDF hardware access feature by setting the <b>UmdfDirectHardwareAccess</b> directive to <b>AllowDirectHardwareAccess</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
HRESULT
CMyDevice::OnPrepareHardware(
    __in IWDFDevice3 * pWdfDevice,
    __in IWDFCmResourceList * pRaw,
    __in IWDFCmResourceList * pTrans
    ) 
{
    PCM_PARTIAL_RESOURCE_DESCRIPTOR desc = NULL;
    PHYSICAL_ADDRESS regBasePA = {0};
    ULONG regLength = 0;
    BOOLEAN found = FALSE;
    HRESULT hr = S_OK;

    //
    // Scan the list to identify our resource.
    //
    for (i=0; i < pWdfResTranslated->GetCount(); i++) {
        desc = (PCM_PARTIAL_RESOURCE_DESCRIPTOR) pTrans->GetDescriptor(i);

        switch (desc->Type) {
            case CmResourceTypeMemory:
                //
                // See if this is the memory resource we’re looking for.
                // 
                if (desc->u.Memory.Length == 0x200) {
                    regsBasePA = desc->u.Memory.Start;
                    regsLength = desc->u.Memory.Length;
                    found = TRUE;                    
                }
                break;

            default:
                // Ignore all other descriptors.
                break;
        }
    }

    //
    // Map the resource. Store the register base in partner device
    // object for later access.
    //
    if (found) {
            hr = pWdfDevice->MapIoSpace(regBasePA,
                                           regLengthlength, 
                                           MmNonCached,
                                          (void **)&m_RegBase);
            if (SUCCEEDED(hr)) {
            //
            // Store the register range in partner object. This will 
            // be needed for unmapping.
            //
            m_RegLength = regLength;
        }
    }

    …
}

//
// UMDF driver uses one of the register access APIs such as
// WRITE_REGISTER_Xxx or READ_REGISTER_Xxx macros to access device register.
//
VOID
CMyQueue::WriteToDevice(
    __in IWDFDevice3* pWdfDevice,
    __in UCHAR Value
    )
{
    //
    // Write the UCHAR value at offset 2 from register base.
    //
    WRITE_REGISTER_UCHAR(pWdfDevice, 
                      (m_MyDevice->m_RegBase)+2, 
                       Value);
}

HRESULT
CMyDevice::OnReleaseHardware(
    __in IWDFDevice3 * pWdfDevice,
    __in IWDFCmResourceList * pTrans
    )
{
    //
    // Unmap registers memory resource.
    //
    pWdfDevice->UnmapIoSpace(m_RegBase, m_RegLength);

    return S_OK;
}

</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a>
 

 

