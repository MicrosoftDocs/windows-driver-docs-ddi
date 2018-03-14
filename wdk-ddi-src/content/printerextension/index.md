---
UID: NA:printerextension
ms.assetid: 39fec125-0979-3b7b-9916-abfd53378c86
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Printerextension.h header



This header is used by print. For more information, see
- [print](../_print/index.md)

Printerextension.h contain these programming interfaces:


## Enumerations

| Title   | Description   |
| ---- |:---- |
| [tagPrintJobStatus enumeration](ne-printerextension-tagprintjobstatus.md) | This enumeration is a one-to-one mapping to the spooler flags suppled in the JOB_INFO_X structures. |
| [tagPrintSchemaConstrainedSetting enumeration](ne-printerextension-tagprintschemaconstrainedsetting.md) | The PrintSchemaConstrainedSetting enumeration specifies whether the Option is available based on the current device configuration. The constrained attribute appears only in a PrintCapabilities document. |
| [tagPrintSchemaParameterDataType enumeration](ne-printerextension-tagprintschemaparameterdatatype.md) | The PrintSchemaParameterDataType enumeration identifies the allowed data types for the Print Schema parameter. |
| [tagPrintSchemaSelectionType enumeration](ne-printerextension-tagprintschemaselectiontype.md) | The PrintSchemaSelectionType enumeration identifies how a Feature’s options should be selected. This property appears only in a PrintCapabilities document. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IPrintJob interface](nn-printerextension-iprintjob.md) | Contains properties that represent a print job. |
| [IPrintJobCollection interface](nn-printerextension-iprintjobcollection.md) | This interfaces provides an enumeration of the jobs in the print queue. |
| [IPrintSchemaAsyncOperation interface](nn-printerextension-iprintschemaasyncoperation.md) | Represents an asynchronous operation context for validation, merge or commit operations. |
| [IPrintSchemaAsyncOperationEvent interface](nn-printerextension-iprintschemaasyncoperationevent.md) | Exposes a validation, merge, or commit completion event delegate. |
| [IPrintSchemaCapabilities interface](nn-printerextension-iprintschemacapabilities.md) | Provides the primary method to access PrintCapabilities. |
| [IPrintSchemaCapabilities2 interface](nn-printerextension-iprintschemacapabilities2.md) | The IPrintSchemaCapabilities2 interface represents an extension to the IPrintSchemaCapabilities object, which provides wrapper methods over a print capabilities document. |
| [IPrintSchemaDisplayableElement interface](nn-printerextension-iprintschemadisplayableelement.md) | Provides the displayable string for a PrintCapabilites PrintSchema element. |
| [IPrintSchemaElement interface](nn-printerextension-iprintschemaelement.md) | Provides access to the underlying XML node and &#0034;name&#0034; attribute information for a Print Schema element. |
| [IPrintSchemaFeature interface](nn-printerextension-iprintschemafeature.md) | Exposes a Print Schema Feature element. |
| [IPrintSchemaNUpOption interface](nn-printerextension-iprintschemanupoption.md) | Exposes a Print Schema NUp Option element. |
| [IPrintSchemaOption interface](nn-printerextension-iprintschemaoption.md) | Exposes a Print Schema Option object. |
| [IPrintSchemaOptionCollection interface](nn-printerextension-iprintschemaoptioncollection.md) | Exposes a collection of IPrintSchemaOption objects. |
| [IPrintSchemaPageImageableSize interface](nn-printerextension-iprintschemapageimageablesize.md) | Exposes the PageImageableSize property of PrintCapabilities. The properties of this interface map directly to those in the PageImageableSize property of PrintCapabilities. |
| [IPrintSchemaPageMediaSizeOption interface](nn-printerextension-iprintschemapagemediasizeoption.md) | Exposes a Print Schema PageMediaSize Option element. |
| [IPrintSchemaParameterDefinition interface](nn-printerextension-iprintschemaparameterdefinition.md) | The IPrintSchemaParameterDefinition interface represents a parameter definition, as defined in the Print Schema Specification. |
| [IPrintSchemaParameterInitializer interface](nn-printerextension-iprintschemaparameterinitializer.md) | The IPrintSchemaParameterInitializer interface represents a parameter initialization value, as defined in the print schema specification. |
| [IPrintSchemaTicket interface](nn-printerextension-iprintschematicket.md) | Provides the primary method to access and validate a PrintTicket. |
| [IPrintSchemaTicket2 interface](nn-printerextension-iprintschematicket2.md) | The IPrintSchemaTicket2 interface is an extension to the IPrintSchemaTicket interface, which provides wrapper methods over a print ticket document. |
| [IPrinterBidiSetRequestCallback interface](nn-printerextension-iprinterbidisetrequestcallback.md) | Describes the signature of the callback object that receives the Bidi response. |
| [IPrinterExtensionAsyncOperation interface](nn-printerextension-iprinterextensionasyncoperation.md) | Provides the context associated with an asynchronous operation. |
| [IPrinterExtensionContext interface](nn-printerextension-iprinterextensioncontext.md) | Represents the context for the activation of a UWP device app for printers. |
| [IPrinterExtensionContextCollection interface](nn-printerextension-iprinterextensioncontextcollection.md) | Exposes a collection of IPrinterExtensionContext objects. |
| [IPrinterExtensionEvent interface](nn-printerextension-iprinterextensionevent.md) | The IPrinterExtensionEvent interface represents the event delegate implemented by desktop printer extensions for activation. |
| [IPrinterExtensionEventArgs interface](nn-printerextension-iprinterextensioneventargs.md) | Represents the context for the desktop printer extension activation. |
| [IPrinterExtensionManager interface](nn-printerextension-iprinterextensionmanager.md) | The IPrinterExtensionManager interface is retrieved by CoCreating the PrinterExtensionManager class. |
| [IPrinterExtensionRequest interface](nn-printerextension-iprinterextensionrequest.md) | Completes the given extension event with either a cancellation or success. |
| [IPrinterPropertyBag interface](nn-printerextension-iprinterpropertybag.md) | Provides strongly-typed get and set methods. |
| [IPrinterQueue interface](nn-printerextension-iprinterqueue.md) | Represents a single printer queue. |
| [IPrinterQueue2 interface](nn-printerextension-iprinterqueue2.md) | Represents a single printer queue. |
| [IPrinterQueueEvent interface](nn-printerextension-iprinterqueueevent.md) | Provides the event delegate for printer queue events. |
| [IPrinterQueueView interface](nn-printerextension-iprinterqueueview.md) | Provides a way to change the range of print jobs being monitored. |
| [IPrinterQueueViewEvent interface](nn-printerextension-iprinterqueueviewevent.md) | Provides the signature of the event handler. |
| [IPrinterScriptContext interface](nn-printerextension-iprinterscriptcontext.md) | Passed to all third-party constraints JavaScript functions, and provides access to relevant objects. |
| [IPrinterScriptablePropertyBag interface](nn-printerextension-iprinterscriptablepropertybag.md) | The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients. |
| [IPrinterScriptablePropertyBag2 interface](nn-printerextension-iprinterscriptablepropertybag2.md) | "." |
| [IPrinterScriptableSequentialStream interface](nn-printerextension-iprinterscriptablesequentialstream.md) | The IPrinterScriptableSequentialStream interface is an ISequentialStream-like interface that works in JavaScript. Instead of reading and writing byte arrays, it reads and writes JavaScript arrays of bytes, which are values between 0 and 255. |
| [IPrinterScriptableStream interface](nn-printerextension-iprinterscriptablestream.md) | The IPrinterScriptableStream interface builds on IPrinterScriptableSequentialStream and adds IStream-like semantics. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IPrintJob::RequestCancel method](nf-printerextension-iprintjob-requestcancel.md) | Requests the cancellation of a print job. |
| [IPrintJob::get_Id method](nf-printerextension-iprintjob-get_id.md) | Gets the print job identifier (ID). |
| [IPrintJob::get_Name method](nf-printerextension-iprintjob-get_name.md) | Gets the name of the printer for this print queue. |
| [IPrintJob::get_PrintedPages method](nf-printerextension-iprintjob-get_printedpages.md) | Gets the number of pages that have been printed. |
| [IPrintJob::get_Status method](nf-printerextension-iprintjob-get_status.md) | Gets the current status of the print job. |
| [IPrintJob::get_SubmissionTime method](nf-printerextension-iprintjob-get_submissiontime.md) | Gets the submission time, in the “DATE” format, provided in the user’s local time (not in the UTC format that is provided by the spooler). |
| [IPrintJob::get_TotalPages method](nf-printerextension-iprintjob-get_totalpages.md) | Gets the total number of pages that the document contains. |
| [IPrintJobCollection::GetAt method](nf-printerextension-iprintjobcollection-getat.md) | Gets a pointer to an IPrintJob object. |
| [IPrintJobCollection::get_Count method](nf-printerextension-iprintjobcollection-get_count.md) | Gets a count of the number of IPrinterExtensionContext objects in the collection. |
| [IPrintSchemaAsyncOperation::Cancel method](nf-printerextension-iprintschemaasyncoperation-cancel.md) | Cancels the asynchronous PrintSchema operation. |
| [IPrintSchemaAsyncOperation::Start method](nf-printerextension-iprintschemaasyncoperation-start.md) | Starts the asynchronous PrintSchema operation. |
| [IPrintSchemaAsyncOperationEvent::Completed method](nf-printerextension-iprintschemaasyncoperationevent-completed.md) | Is called when asynchronous PrintSchema operation that is represented by an IPrintSchemaAsyncOperation context is completed. |
| [IPrintSchemaCapabilities2::GetParameterDefinition method](nf-printerextension-iprintschemacapabilities2-getparameterdefinition.md) | The GetParameterDefinition method retrieves the IPrintSchemaParameterDefinition object, and it represents the &lt;psf |
| [IPrintSchemaCapabilities::GetFeature method](nf-printerextension-iprintschemacapabilities-getfeature.md) | Gets a named feature from the PrintCapabilities, by name and full namespace URI. |
| [IPrintSchemaCapabilities::GetFeatureByKeyName method](nf-printerextension-iprintschemacapabilities-getfeaturebykeyname.md) | Gets a feature from the PrintCapabilities based on a given key name. |
| [IPrintSchemaCapabilities::GetOptions method](nf-printerextension-iprintschemacapabilities-getoptions.md) | Gets all the options of a feature. |
| [IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket method](nf-printerextension-iprintschemacapabilities-getselectedoptioninprintticket.md) | Gets the selected option for a feature in IPrintSchemaTicket. |
| [IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMaxValue method](nf-printerextension-iprintschemacapabilities-get_jobcopiesalldocumentsmaxvalue.md) | Gets the JobCopiesAllDocuments parameter maximum value. |
| [IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue method](nf-printerextension-iprintschemacapabilities-get_jobcopiesalldocumentsminvalue.md) | Gets the JobCopiesAllDocuments parameter minimum value. |
| [IPrintSchemaCapabilities::get_PageImageableSize method](nf-printerextension-iprintschemacapabilities-get_pageimageablesize.md) | Gets the imageable area information of the printer. |
| [IPrintSchemaDisplayableElement::get_DisplayName method](nf-printerextension-iprintschemadisplayableelement-get_displayname.md) | Gets a displayable string for this item. |
| [IPrintSchemaElement::get_Name method](nf-printerextension-iprintschemaelement-get_name.md) | Gets the name of the printer for this print queue. |
| [IPrintSchemaElement::get_NamespaceUri method](nf-printerextension-iprintschemaelement-get_namespaceuri.md) | Gets the namespace URI value of the &#0034;name&#0034; attribute of this node. |
| [IPrintSchemaElement::get_XmlNode method](nf-printerextension-iprintschemaelement-get_xmlnode.md) | Gets the IXMLDOMNode object associated with this item. |
| [IPrintSchemaFeature::GetOption method](nf-printerextension-iprintschemafeature-getoption.md) | Gets the option with the given name. |
| [IPrintSchemaFeature::get_DisplayUI method](nf-printerextension-iprintschemafeature-get_displayui.md) | Gets the setting that indicates whether or not to show the print UI. |
| [IPrintSchemaFeature::get_SelectedOption method](nf-printerextension-iprintschemafeature-get_selectedoption.md) | Changes the selected option of the Print Schema Feature element to the specified IPrintSchemaOption element. |
| [IPrintSchemaFeature::get_SelectionType method](nf-printerextension-iprintschemafeature-get_selectiontype.md) | Gets the selection type of the Feature. |
| [IPrintSchemaFeature::put_SelectedOption method](nf-printerextension-iprintschemafeature-put_selectedoption.md) | Changes the selected option of the Print Schema Feature element to the specified IPrintSchemaOption element. |
| [IPrintSchemaNUpOption::get_PagesPerSheet method](nf-printerextension-iprintschemanupoption-get_pagespersheet.md) | Gets the number of pages per sheet. |
| [IPrintSchemaOption::GetPropertyValue method](nf-printerextension-iprintschemaoption-getpropertyvalue.md) | Gets the XML node for the &#0034;value&#0034; child element of a &#0034;Property&#0034; or a &#0034;ScoredProperty&#0034; element with the given name. |
| [IPrintSchemaOption::get_Constrained method](nf-printerextension-iprintschemaoption-get_constrained.md) | Gets the constraint setting type for the schema option. |
| [IPrintSchemaOption::get_Selected method](nf-printerextension-iprintschemaoption-get_selected.md) | Indicates whether this option is selected. |
| [IPrintSchemaOptionCollection::GetAt method](nf-printerextension-iprintschemaoptioncollection-getat.md) | Gets a pointer to an IPrintSchemaOption object. |
| [IPrintSchemaOptionCollection::get_Count method](nf-printerextension-iprintschemaoptioncollection-get_count.md) | Gets a count of the number of IPrinterExtensionContext objects in the collection. |
| [IPrintSchemaPageImageableSize::get_ExtentHeightInMicrons method](nf-printerextension-iprintschemapageimageablesize-get_extentheightinmicrons.md) | Gets the vertical distance between the origin and the bounding limit of the canvas application media size. |
| [IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons method](nf-printerextension-iprintschemapageimageablesize-get_extentwidthinmicrons.md) | Gets the horizontal distance between the origin and the bounding limit of the application media size. |
| [IPrintSchemaPageImageableSize::get_ImageableSizeHeightInMicrons method](nf-printerextension-iprintschemapageimageablesize-get_imageablesizeheightinmicrons.md) | Gets the vertical dimension of the application media size relative to the page orientation. |
| [IPrintSchemaPageImageableSize::get_ImageableSizeWidthInMicrons method](nf-printerextension-iprintschemapageimageablesize-get_imageablesizewidthinmicrons.md) | Gets the horizontal dimension of the application media size relative to the page orientation. |
| [IPrintSchemaPageImageableSize::get_OriginHeightInMicrons method](nf-printerextension-iprintschemapageimageablesize-get_originheightinmicrons.md) | Gets the vertical origin of the imageable area relative to the application media size. |
| [IPrintSchemaPageImageableSize::get_OriginWidthInMicrons method](nf-printerextension-iprintschemapageimageablesize-get_originwidthinmicrons.md) | Gets the horizontal origin of the imageable area relative to the application media size. |
| [IPrintSchemaPageMediaSizeOption::get_HeightInMicrons method](nf-printerextension-iprintschemapagemediasizeoption-get_heightinmicrons.md) | Gets the height of the page in microns. |
| [IPrintSchemaPageMediaSizeOption::get_WidthInMicrons method](nf-printerextension-iprintschemapagemediasizeoption-get_widthinmicrons.md) | Gets the width of the page in microns. |
| [IPrintSchemaParameterDefinition::get_DataType method](nf-printerextension-iprintschemaparameterdefinition-get_datatype.md) | The DataType property gets the PrintSchemaParameterDataType enumerated value that indicates the expected data type for the Print Schema parameter. |
| [IPrintSchemaParameterDefinition::get_RangeMax method](nf-printerextension-iprintschemaparameterdefinition-get_rangemax.md) | The RangeMax property gets the maximum value of the allowed data range. |
| [IPrintSchemaParameterDefinition::get_RangeMin method](nf-printerextension-iprintschemaparameterdefinition-get_rangemin.md) | The RangeMin property gets the minimum value of the allowed data range. |
| [IPrintSchemaParameterDefinition::get_UnitType method](nf-printerextension-iprintschemaparameterdefinition-get_unittype.md) | The UnitType property gets the unit type. |
| [IPrintSchemaParameterDefinition::get_UserInputRequired method](nf-printerextension-iprintschemaparameterdefinition-get_userinputrequired.md) | The UserInputRequired property gets the Boolean value that indicates whether or not a user input value is required for the Print Schema parameter. |
| [IPrintSchemaParameterInitializer::get_Value method](nf-printerextension-iprintschemaparameterinitializer-get_value.md) | The Value (get_Value) property gets the current value of the IPrintSchemaParameterInitializer object. |
| [IPrintSchemaParameterInitializer::put_Value method](nf-printerextension-iprintschemaparameterinitializer-put_value.md) | The Value (get_Value) property gets the current value of the IPrintSchemaParameterInitializer object. |
| [IPrintSchemaTicket2::GetParameterInitializer method](nf-printerextension-iprintschematicket2-getparameterinitializer.md) | The GetParameterInitializer method retrieves the IPrintSchemaParameterInitializer object, and it represents the &lt;psf |
| [IPrintSchemaTicket::CommitAsync method](nf-printerextension-iprintschematicket-commitasync.md) | Gets an asynchronous PrintTicket commit operation context. |
| [IPrintSchemaTicket::GetCapabilities method](nf-printerextension-iprintschematicket-getcapabilities.md) | Gets an IPrintSchemaCapabilities object that represents the printer capabilities based on the current settings of this IPrintSchemaTicket object. |
| [IPrintSchemaTicket::GetFeature method](nf-printerextension-iprintschematicket-getfeature.md) | Gets a named feature from the PrintTicket, by name and full namespace URI. |
| [IPrintSchemaTicket::GetFeatureByKeyName method](nf-printerextension-iprintschematicket-getfeaturebykeyname.md) | Gets a feature from the PrintTicket based on the specified key name. |
| [IPrintSchemaTicket::NotifyXmlChanged method](nf-printerextension-iprintschematicket-notifyxmlchanged.md) | Notifies the print system that the XML DOM object has changed. |
| [IPrintSchemaTicket::ValidateAsync method](nf-printerextension-iprintschematicket-validateasync.md) | Gets an asynchronous PrintTicket validation operation context. |
| [IPrintSchemaTicket::get_JobCopiesAllDocuments method](nf-printerextension-iprintschematicket-get_jobcopiesalldocuments.md) | Gets the copy count. |
| [IPrintSchemaTicket::put_JobCopiesAllDocuments method](nf-printerextension-iprintschematicket-put_jobcopiesalldocuments.md) | Gets the copy count. |
| [IPrinterBidiSetRequestCallback::Completed method](nf-printerextension-iprinterbidisetrequestcallback-completed.md) | Invoked when the Bidi “Set”” operation is completed. |
| [IPrinterExtensionAsyncOperation::Cancel method](nf-printerextension-iprinterextensionasyncoperation-cancel.md) | Cancels the asynchronous operation. |
| [IPrinterExtensionContext::get_DriverProperties method](nf-printerextension-iprinterextensioncontext-get_driverproperties.md) | Gets the driver property bag. |
| [IPrinterExtensionContext::get_PrintSchemaTicket method](nf-printerextension-iprinterextensioncontext-get_printschematicket.md) | Gets the print ticket that is appropriate for the queue and the activation. |
| [IPrinterExtensionContext::get_PrinterQueue method](nf-printerextension-iprinterextensioncontext-get_printerqueue.md) | Gets the queue for the printer. |
| [IPrinterExtensionContext::get_UserProperties method](nf-printerextension-iprinterextensioncontext-get_userproperties.md) | Gets the user property bag for this app. |
| [IPrinterExtensionContextCollection::GetAt method](nf-printerextension-iprinterextensioncontextcollection-getat.md) | Gets a pointer to an IPrinterExtensionContext object. |
| [IPrinterExtensionContextCollection::get_Count method](nf-printerextension-iprinterextensioncontextcollection-get_count.md) | Gets a count of the number of IPrinterExtensionContext objects in the collection. |
| [IPrinterExtensionContextCollection::get__NewEnum method](nf-printerextension-iprinterextensioncontextcollection-get__newenum.md) | Gets a pointer to the enumerants of IPrinterExtensionContextCollection objects. |
| [IPrinterExtensionEvent::OnDriverEvent method](nf-printerextension-iprinterextensionevent-ondriverevent.md) | Called when a driver event occurs. |
| [IPrinterExtensionEvent::OnPrinterQueuesEnumerated method](nf-printerextension-iprinterextensionevent-onprinterqueuesenumerated.md) | Called when printer queues are enumerated. |
| [IPrinterExtensionEventArgs::get_BidiNotification method](nf-printerextension-iprinterextensioneventargs-get_bidinotification.md) | Gets the text of the bidirectional communication (Bidi) notification, if applicable. |
| [IPrinterExtensionEventArgs::get_DetailedReasonId method](nf-printerextension-iprinterextensioneventargs-get_detailedreasonid.md) | Gets a more detailed activation reason than what can be retrieved from ReasonId. |
| [IPrinterExtensionEventArgs::get_ReasonId method](nf-printerextension-iprinterextensioneventargs-get_reasonid.md) | Gets the reason why the printer extension was activated. |
| [IPrinterExtensionEventArgs::get_Request method](nf-printerextension-iprinterextensioneventargs-get_request.md) | Gets the IPrinterExtensionRequest object for the current event. |
| [IPrinterExtensionEventArgs::get_SourceApplication method](nf-printerextension-iprinterextensioneventargs-get_sourceapplication.md) | Gets the name of the application that invoked the printer extension. |
| [IPrinterExtensionEventArgs::get_WindowModal method](nf-printerextension-iprinterextensioneventargs-get_windowmodal.md) | Gets the run mode parameter that determines whether or not the printer extension should be run as modal. |
| [IPrinterExtensionEventArgs::get_WindowParent method](nf-printerextension-iprinterextensioneventargs-get_windowparent.md) | Gets the handle of the parent window. |
| [IPrinterExtensionManager::DisableEvents method](nf-printerextension-iprinterextensionmanager-disableevents.md) | Disallows events to be generated. |
| [IPrinterExtensionManager::EnableEvents method](nf-printerextension-iprinterextensionmanager-enableevents.md) | The EnableEvents method allows events to be generated for the specified printer driver until DisableEvents is called. |
| [IPrinterExtensionRequest::Cancel method](nf-printerextension-iprinterextensionrequest-cancel.md) | Completes the extension event with a cancellation. |
| [IPrinterExtensionRequest::Complete method](nf-printerextension-iprinterextensionrequest-complete.md) | Completes the extension event. |
| [IPrinterPropertyBag::GetBool method](nf-printerextension-iprinterpropertybag-getbool.md) | Reads a specified boolean property. |
| [IPrinterPropertyBag::GetBytes method](nf-printerextension-iprinterpropertybag-getbytes.md) | Reads a byte array property. |
| [IPrinterPropertyBag::GetInt32 method](nf-printerextension-iprinterpropertybag-getint32.md) | Reads an integer property. |
| [IPrinterPropertyBag::GetReadStream method](nf-printerextension-iprinterpropertybag-getreadstream.md) | Gets a stream in order to read from a stream property. |
| [IPrinterPropertyBag::GetString method](nf-printerextension-iprinterpropertybag-getstring.md) | Reads a string property. |
| [IPrinterPropertyBag::GetWriteStream method](nf-printerextension-iprinterpropertybag-getwritestream.md) | Gets a stream in order to write a stream property. |
| [IPrinterPropertyBag::SetBool method](nf-printerextension-iprinterpropertybag-setbool.md) | Writes a specified boolean property value. |
| [IPrinterPropertyBag::SetBytes method](nf-printerextension-iprinterpropertybag-setbytes.md) | Writes a byte array property. |
| [IPrinterPropertyBag::SetInt32 method](nf-printerextension-iprinterpropertybag-setint32.md) | Writes an integer property. |
| [IPrinterPropertyBag::SetString method](nf-printerextension-iprinterpropertybag-setstring.md) | Writes a string property. |
| [IPrinterQueue2::GetPrinterQueueView method](nf-printerextension-iprinterqueue2-getprinterqueueview.md) | Retrieves an IPrinterQueueView object, and initializes the object with the range of jobs to be monitored. |
| [IPrinterQueue2::SendBidiSetRequestAsync method](nf-printerextension-iprinterqueue2-sendbidisetrequestasync.md) | Uses an XML string value to send a Bidi Set request as an asynchronous operation. |
| [IPrinterQueue::GetProperties method](nf-printerextension-iprinterqueue-getproperties.md) | Gets the properties in the property bag for the queue. |
| [IPrinterQueue::SendBidiQuery method](nf-printerextension-iprinterqueue-sendbidiquery.md) | Performs an asynchronous refresh operation with the specified query, and invokes the IPrinterQueueEvent |
| [IPrinterQueue::get_Handle method](nf-printerextension-iprinterqueue-get_handle.md) | Gets the underlying native handle for this print queue. |
| [IPrinterQueue::get_Name method](nf-printerextension-iprinterqueue-get_name.md) | Gets the name of the printer for this print queue. |
| [IPrinterQueueEvent::OnBidiResponseReceived method](nf-printerextension-iprinterqueueevent-onbidiresponsereceived.md) | Called when a bidi response is received. |
| [IPrinterQueueView::SetViewRange method](nf-printerextension-iprinterqueueview-setviewrange.md) | Sets the range of print jobs being monitored. |
| [IPrinterQueueViewEvent::OnChanged method](nf-printerextension-iprinterqueueviewevent-onchanged.md) | Provides an IPrintJobCollection object that provides a snapshot of a range of print jobs in the queue. |
| [IPrinterScriptContext::get_DriverProperties method](nf-printerextension-iprinterscriptcontext-get_driverproperties.md) | Gets the driver property bag. |
| [IPrinterScriptContext::get_QueueProperties method](nf-printerextension-iprinterscriptcontext-get_queueproperties.md) | Provides access to the queue property bag, if the property bag is present. |
| [IPrinterScriptContext::get_UserProperties method](nf-printerextension-iprinterscriptcontext-get_userproperties.md) | Gets the user property bag for this app. |
| [IPrinterScriptablePropertyBag2::GetReadStreamAsXML method](nf-printerextension-iprinterscriptablepropertybag2-getreadstreamasxml.md) | "." |
| [IPrinterScriptablePropertyBag::GetBool method](nf-printerextension-iprinterscriptablepropertybag-getbool.md) | Gets a specified boolean property. |
| [IPrinterScriptablePropertyBag::GetBytes method](nf-printerextension-iprinterscriptablepropertybag-getbytes.md) | Gets a byte array property. |
| [IPrinterScriptablePropertyBag::GetInt32 method](nf-printerextension-iprinterscriptablepropertybag-getint32.md) | Gets an integer property. |
| [IPrinterScriptablePropertyBag::GetReadStream method](nf-printerextension-iprinterscriptablepropertybag-getreadstream.md) | Gets a read stream and uses it to read from a property. |
| [IPrinterScriptablePropertyBag::GetString method](nf-printerextension-iprinterscriptablepropertybag-getstring.md) | Gets a string property. |
| [IPrinterScriptablePropertyBag::GetWriteStream method](nf-printerextension-iprinterscriptablepropertybag-getwritestream.md) | Gets a stream and uses it to write to a stream property. |
| [IPrinterScriptablePropertyBag::SetBool method](nf-printerextension-iprinterscriptablepropertybag-setbool.md) | Writes a specified boolean property value. |
| [IPrinterScriptablePropertyBag::SetBytes method](nf-printerextension-iprinterscriptablepropertybag-setbytes.md) | Writes a byte array property. |
| [IPrinterScriptablePropertyBag::SetInt32 method](nf-printerextension-iprinterscriptablepropertybag-setint32.md) | Writes an integer property. |
| [IPrinterScriptablePropertyBag::SetString method](nf-printerextension-iprinterscriptablepropertybag-setstring.md) | Writes a string property. |
| [IPrinterScriptableSequentialStream::Read method](nf-printerextension-iprinterscriptablesequentialstream-read.md) | The Read method reads bytes from the stream and returns them as a JavaScript array. |
| [IPrinterScriptableSequentialStream::Write method](nf-printerextension-iprinterscriptablesequentialstream-write.md) | The Write method writes the provided JavaScript array to the stream and returns the number of bytes written. |
| [IPrinterScriptableStream::Commit method](nf-printerextension-iprinterscriptablestream-commit.md) | Commits the operation. |
| [IPrinterScriptableStream::Seek method](nf-printerextension-iprinterscriptablestream-seek.md) | Sets the seek pointer. |
| [IPrinterScriptableStream::SetSize method](nf-printerextension-iprinterscriptablestream-setsize.md) | Sets the size of the scriptable stream, in bytes. |
