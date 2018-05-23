# Change on version numbering and wsdl configuration

## Change on version numbering
Version numbering has been changed due to releasing new versions on regular basis.
* Before change <br>
VX.X (example: V6.5)
* After the change of V201805 <br>
VYYYYMM (example: V201805)

## Change on wsdl configuration (Namespace fragmentation)
In order to clear the issue of duplicating entities by auto generation occured on a few environements, we made a change of NameSpace fragmentation and object configuration change.

* Before change <br>
http://ss.yahooapis.jp/V6
* After the change of V201805 <br>
http://ss.yahooapis.jp/V201805 <br>
http://ss.yahooapis.jp/V201805/ServiceName <br> (example: Account, Campaign, AdGroup)

### Elements belong to NameSpace after change
#### Elements used across Services
On SOAP Request/Response, common entities on each service are aggregated to the following NameSpace.
<table class="standard">
<tbody>
<tr>
<th>
NameSpace
</th>
<th>
Element (Entity)
</th>
<th>
Description
</th>
</tr>
<tr>
 <td valign="top" rowspan=8>http://ss.yahooapis.jp/V201805</td>
 <td valign="top">SoapHeader<br>
 ・license<br>
 ・apiAccountId<br>
 ・apiAccountPassword<br>
 ・accountId<br>
 ・onBehalfOfAccountId<br>
 ・onBehalfOfPassword
 </td>
 <td valign="top">Soap header (authentication information)<br>
 ・License<br>
 ・API account ID<br>
 ・API account password<br>
 ・Account ID<br>
 ・On behalf of account ID<br>
 ・On behalf of account password<br>
 </td>
</tr>
<tr>
 <td valign="top">SoapResponseHeader<br>
 ・service<br>
 ・timeTakenSeconds<br>
 ・requestTime
 </td>
 <td valign="top">Soap Response header<br>
 ・Service name<br>
 ・Process time taken in second<br>
 ・Time the process requested (Unix time stamp) <br>
 </td>
</tr>
<tr>
 <td valign="top">Paging<br>
 ・startIndex<br>
 ・numberResults
 </td>
 <td valign="top">Paging<br>
 ・Index of start paging<br>
 ・Maximum available number of paging
</td>
</tr>
<tr>
 <td valign="top">Error<br>
 ・code<br>
 ・message<br>
 ・detail
 </td>
 <td valign="top">Error information<br>
 ・Error code<br>
 ・Error message<br>
 ・Error details
 </td>
</tr>
<tr>
 <td valign="top">ErrorDetail<br>
 ・requestKey<br>
 ・requestValue
 </td>
 <td valign="top">Error information in detail<br>
 ・Error item<br>
 ・Error value
 </td>
</tr>
<tr>
 <td valign="top">Page<br>
 ・totalNumEntries<br>
 ・Page.Type</td>
 <td valign="top">Execution result of get method<br>
 ・Total number of paging (not by each page, total number)<br>
 ・ServiceName +'Page'
 </td>
</tr>
<tr>
 <td valign="top">ReturnValue<br>
 ・operationSucceeded<br>
 ・error
 </td>
 <td valign="top">Execution result of get/mutate method<br>
 ・Whether the operation process succeeded or not<br>
 ・Error information</td>
</tr>
<tr>
 <td valign="top">ListReturnValue<br>
 ・ListReturnValue.Type<br>
 ・Operation.Type</td>
 <td valign="top">Execution result of mutate method<br>
 ・ServiceName ＋'ReturnValue'<br>
 ・'ADD' or 'SET' or 'REMOVE'
 </td>
</tr>
</table>

#### Service specific element
On SOAP Request/Response, service specific entity/enum are aggregated to the following NameSpace of each service.
</table>
<table class="standard">
<tbody>
<tr>
<th>
NameSpace
</th>
<th>
Element (Entity, Enum)
</th>
</tr>
<tr>
 <td valign="top">http://ss.yahooapis.jp/V201805/ServiceName</td>
 <td valign="top">Service specific element<br>
 (example: 〜Selector, 〜Operation, Ad, AdGroup, Campaign, AdType) </td>
 </td>
</tr>

