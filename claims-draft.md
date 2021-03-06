---
layout: default
title: Content Format for Medical Claims
---

# Content Format for Medical Claims

Blue Button files from health plans typically come from administrative claims databases, as well as potentially self-entered data on Personal Health Records.
 
Data made available to patients via Blue Button+ should be human-readable and formatted in a way that is “machine readable” for third party applications. This section includes recommended data elements and structure, and format options for providing that data to a patient.

To the extent that data holders already have useful and meaningful electronic health data for consumers' Blue Button files, including from administrative claims data, The followinging Data Fields are recommended for inclusion in the Blue Button+ files. The file should should be as consistent as possible – in both structure and content – with the Medicare Blue Button file (available here).

## 1. Sections
Text describing where these sections come from. Medicare data. X12 data.

<table>
   <tr>
      <th class="table-column">Section</th>
      <th class="table-column">Description</th>
      <th class="table-column">Quick Link</th>
   </tr>
   <tr>
      <th>Payer &amp; Coverage Information</th>
      <td>...</td>
      <td><a href="#payer">Jump to Section</a></td>
   </tr>
   <tr class="odd">
      <th>Patient Information</th>
      <td>...</td>
      <td><a href="#patient">Jump to Section</a></td>
   </tr>
   <tr class="odd">
      <th>Claims</th>
      <td>...</td>
      <td><a href="#claims">Jump to Section</a></td>
   </tr>
</table>

## 2. Breakdown of XML

### Payer & Coverage Information {#payer}

<table>
   <tr>
      <th class="table-column">Field</th>
      <th class="table-column">Description</th>
      <th class="table-column">Example</th>
   </tr>
   <tr>
      <th>Name</th>
      <td>...</td>
      <td>Medicare</td>
   </tr>
   <tr>
      <th>Payer ID</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Payer ID Type</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Plan Name</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Plan ID</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Member Name</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Member ID</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Website</th>
      <td>...</td>
      <td>...</td>
   </tr>
</table>

The following is the XML representation:

{% highlight xml %}
   <payer>
      <name>Name of Insurance</name>
      <payer_id>123456</payer_id>
      <payer_id_type>National Payer ID</payer_id_type>
      <plan_name>Name of Policy</plan_name>
      <plan_id>123456</plan_id>
      <member_id>W1234123456</member_id>
      <member_name>Name of Plan Member</member_name>
      <url>http://yourinsurer.org</url>
   </payer>
{% endhighlight %}

### Patient Information {#patient}

<table>
   <tr>
      <th class="table-column">Field</th>
      <th class="table-column">Description</th>
      <th class="table-column">Example</th>
   </tr>
   <tr>
      <th>Name</th>
      <td>...</td>
      <td>Ellen Harrision Lu</td>
   </tr>
   <tr>
      <th>Patient Identifier</th>
      <td>...</td>
      <td>Member ID</td>
   </tr>
</table>

The following is the XML representation:

{% highlight xml %}
   <patient>
      <name>Ellen Harrison Lu</name>
      <patient_identifier></patient_identifier>
   </patient>
{% endhighlight %}


### Claims Details {#claims}

There are two level of details for each claim.
1. Summary of the claim
2. Detailed breakdown of the claim

#### Summary of the Claim {#summary-of-claim}

<table>
   <tr>
      <th class="table-column">Field</th>
      <th class="table-column">Description</th>
      <th class="table-column">Example</th>
   </tr>
   <tr>
      <th>Claim Number</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Type of Claim</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Provider Details</th>
      <td>Name, Provider ID, Provider ID Type, Provider Billing Address</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Date</th>
      <td>Start Date and End Date</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Charges</th>
      <td>Price Billed, Insurance Approved, Insurance Paid, Patient Responsibility</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Service</th>
      <td>Name of Service, Code System Name, Service Code</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Diagnosis</th>
      <td>Name of Diagnosis, Code System Name, Diagnosis Code</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Details</th>
      <td>See section below.</td>
      <td>...</td>
   </tr>
</table>


#### Claim Details {#claim-details}

The following is the XML representation:

<table>
   <tr>
      <th class="table-column">Field</th>
      <th class="table-column">Description</th>
      <th class="table-column">Example</th>
   </tr>
   <tr>
      <th>Start Date</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>End Date</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Procedure Code</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Procedure Description</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Modifiers</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Quantity</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Price Billed</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Insurance Approved</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Patient Responsibility</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Place of Service</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Place of Service Code</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Type of Service</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Typer of Service Code</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Rendering Provider Number</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Rendering Provider NPI</th>
      <td>...</td>
      <td>...</td>
   </tr>
</table>

{% highlight xml %}
   <claims>
      <claim>0210336239290</claim>
      <type>Part B</type>
      <provider>
         <name>Inova Health Services</name>
         <provider_id>123456789</provider_id>
         <provider_id_type>National Provider ID</provider_id_type>
         <provider_billing_address>601 OFFICE CENTER DRIVE FORT WASHINGTON, PA 19034</provider_billing_address>
      </provider>
      <date>
         <start_date>20101102</start_date>
         <end_date>20101102</end_date>
      </date>
      <charges>
         <price_billed>1022.5</price_billed>
         <insurance_approved>782.33</insurance_approved>
         <insurance_paid>625.86</insurance_paid>
         <patient_responsibility>156.47</patient_responsibility>
      </charges>
      <service>
         <name>Name of Service Provided</name>
         <code_system_name>CPT</code_system_name>
         <code>28521</code>
      </service>
      <diagnoses>
         <name>Name of Condition</name>
         <code_system_name>CPT</code_system_name>
         <code>28521</code>
      </diagnoses>
      <diagnoses>
         <name>Name of Condition</name>
         <code_system_name>CPT</code_system_name>
         <code>5854</code>
      </diagnoses>
      <details>
         <start_date>20101102</start_date>
         <end_date>20101102</end_date>
         <procedure_code>A0428</procedure_code>
         <procedure_description>Description of Procedure</procedure_description>
         <modifiers>
            <description>Additional details</description>
         </modifiers>
         <quantity>1</quantity>
         <price_billed>275</price_billed>
         <insurance_approved>208.99</insurance_approved>
         <patient_responsibility>66.01</patient_responsibility>
         <place_of_service_code>41</place_of_service_code>
         <place_of_service>Ambulance - Land</place_of_service>
         <type_of_service_code>9</type_of_service_code>
         <type_of_service>Other Medical Services</type_of_service>
         <rendering_provider_number>Q335520003</rendering_provider_number>
         <rendering_provider_npi>1023062544</rendering_provider_npi>
      </details>
      <details>
         <start_date>20101102</start_date>
         <end_date>20101102</end_date>
         <procedure_code>A0428</procedure_code>
         <procedure_description>Description of Procedure</procedure_description>
         <modifiers>
            <description>Additional details</description>
         </modifiers>
         <quantity>1</quantity>
         <price_billed>275</price_billed>
         <insurance_approved>208.99</insurance_approved>
         <patient_responsibility>66.01</patient_responsibility>
         <place_of_service_code>41</place_of_service_code>
         <place_of_service>Ambulance - Land</place_of_service>
         <type_of_service_code>9</type_of_service_code>
         <type_of_service>Other Medical Services</type_of_service>
         <rendering_provider_number>Q335520003</rendering_provider_number>
         <rendering_provider_npi>1023062544</rendering_provider_npi>
      </details>
      <details>
         <start_date>20101102</start_date>
         <end_date>20101102</end_date>
         <procedure_code>A0425</procedure_code>
         <procedure_description>Description of Procedure</procedure_description>
         <modifiers>
            <description>Additional details</description>
         </modifiers>
         <quantity>44</quantity>
         <price_billed>472.5</price_billed>
         <insurance_approved>364.35</insurance_approved>
         <patient_responsibility>108.15</patient_responsibility>
         <place_of_service_code>41</place_of_service_code>
         <place_of_service>Ambulance - Land</place_of_service>
         <type_of_service_code>9</type_of_service_code>
         <type_of_service>Other Medical Services</type_of_service>
         <rendering_provider_number>Q335520003</rendering_provider_number>
         <rendering_provider_npi>1023062544</rendering_provider_npi>
      </details>
   </claims>
 {% endhighlight %}


### Prescription Claims {#prescription-claim}

Claims for prescriptions.

<table>
   <tr>
      <th class="table-column">Field</th>
      <th class="table-column">Description</th>
      <th class="table-column">Example</th>
   </tr>
   <tr>
      <th>Claim</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Type</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Pharmacy</th>
      <td>Name, Provider ID, Provider ID Type, Provider Billing Address</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Date</th>
      <td>...</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Drug</th>
      <td>Name, Code System Name, Code, Fill Number, Days Supply</td>
      <td>...</td>
   </tr>
   <tr>
      <th>Prescriber</th>
      <td>Identifier and Name</td>
      <td>...</td>
   </tr>
</table>

The following is the XML representation:

{% highlight xml %}
    <claims>
      <claim>000000123456</claim>
      <type>Part D</type>
      <pharmacy>
         <name>Costco Pharmacy</name>
         <provider_id>1234567891</provider_id>
         <provider_id_type>National Provider ID</provider_id_type>
         <provider_billing_address>601 FIRST STREET, FORT WASHINGTON, PA 19034</provider_billing_address>
      </pharmacy>
      <date>20071002</date>
      <drug>
         <name>OXISTAT</name>
         <code_system_name>RxNorm</code_system_name>
         <code>00462035860</code>
         <fill_number>0</fill_number>
         <days_supply>30</days_supply>
      </drug>
      <prescriber>
         <identifier>1111111111</identifier>
         <name>Harvey, A. McGehee</name>
      </prescriber>
   </claims>
{% endhighlight %}