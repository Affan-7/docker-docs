
{% if include.product == "admin" %}
  {% assign product_link="[Docker Admin](https://admin.docker.com)" %}
  {% assign invite_button = "**Invite**" %}
  {% assign export_button = "the **Action** icon and then select **Export users as CSV**" %}
  {% if include.layer == "company" %}
    {% assign member_navigation="Select your company in the left navigation drop-down menu, and then select **Users**." %}
    {% assign remove_button = "**Remove user**" %}
  {% else %}
    {% assign member_navigation="Select your organization in the left navigation drop-down menu, and then select **Members**." %}
    {% assign remove_button = "**Remove member**" %}
  {% endif %}
{% else %}
  {% assign product_link="[Docker Hub](https://hub.docker.com)" %}
  {% assign member_navigation="Select **Organizations**, your organization, and then **Members**." %}
  {% assign invite_button = "**Invite members**" %}
  {% assign remove_button = "**Remove member**" %}
  {% assign export_button = "**Export members**" %}
{% endif %}

## Invite members

Owners can invite new members to an organization via Docker ID, email address, or via a CSV file containing email addresses. If an invitee does not have a Docker account, they must create an account and verify their email address before they can accept the invitation to join the organization. When inviting members, their pending invitation occupies a seat.

### Invite members via Docker ID or email address

Use the following steps to invite members to your organization via Docker ID or email address. To invite a large amount of members to your organization via CSV file, see the next section.

1. Sign in to {{ product_link }}{: target="_blank" rel="noopener" class="_"}.
2. {{ member_navigation }}
3. Select {{ invite_button }}.
4. Select **Emails or usernames**.
5. Follow the on-screen instructions to invite members. Invite a maximum of 1000 members and separate multiple entries by comma, semicolon, or space.

  > **Note**
  >
  >  It is recommended that you invite non-administrative users to a team other than the owners team. Members in the owners team will have full access to your organization’s administrative settings.

Pending invitations appear in the table. The invitees receive an email with a link to Docker Hub where they can accept or decline the invitation.

### Invite members via CSV file

To invite multiple members to an organization via a CSV file containing email addresses:

1. Sign in to {{ product_link }}{: target="_blank" rel="noopener" class="_"}.
2. {{ member_navigation }}
3. Select {{ invite_button }}.
4. Select **CSV upload**.
5. Select **Download the template CSV file** to optionally download an example CSV file. The following is an example of the contents of a valid CSV file.
    ```
    email
    docker.user-0@example.com
    docker.user-1@example.com
    ```
  CSV file requirements:
   -  The file must contain a header row with at least one heading named `email`. Additional columns are allowed and are ignored in the import.
   -  The file must contain a maximum of 1000 email addresses (rows). To invite more than 1000 users, create multiple CSV files and perform all steps in this task for each file.
6. Create a new CSV file or export a CSV file from another application.
  - To export a CSV file from another application, see the application’s documentation.
  - To create a new CSV file, open a new file in a text editor, type `email` on the first line, type the user email addresses one per line on the following lines, and then save the file with a .csv extension.
7. Select **Browse files** and then select your CSV file, or drag and drop the CSV file into the **Select a CSV file to upload** box. You can only select one CSV file at a time.
  > **Note**
  >
  > If the amount of email addresses in your CSV file exceeds the number of available seats in your organization, you cannot continue to invite members. To invite members, you can purchase more seats, or remove some email addresses from the CSV file and re-select the new file. To purchase more seats, see [Add seats to your subscription](/subscription/add-seats/) or [Contact sales](https://www.docker.com/pricing/contact-sales/).
8. After the CSV file has been uploaded, select **Review**.
  Valid email addresses and any email addresses that have issues appear.
  Email addresses may have the following issues:
	  - **Invalid email**: The email address is not a valid address. The email address will be ignored if you send invites. You can correct the email address in the CSV file and re-import the file.
	  - **Already invited**: The user has already been sent an invite email and another invite email will not be sent.
	  - **Member**: The user is already a member of your organization and an invite email will not be sent.
	  - **Duplicate**: The CSV file has multiple occurrences of the same email address. The user will be sent only one invite email.
9. Follow the on-screen instructions to invite members.

  > **Note**
  >
  >  It is recommended that you invite non-administrative users to a team other than the owners team. Members in the owners team will have full access to your organization’s administrative settings.


Pending invitations appear in the table. The invitees receive an email with a link to Docker Hub where they can accept or decline the invitation.

## Resend invitations

To resend an invitation if the invite is pending or declined:

1. Sign in to {{ product_link }}{: target="_blank" rel="noopener" class="_"}.
2. {{ member_navigation }}
3. In the table, locate the invitee, select the **Action** icon, and then select **Resend invitation**.
4. Select **Invite** to confirm.

## Remove a member or invitee

To remove a member from an organization:

1. Sign in to {{ product_link }}{: target="_blank" rel="noopener" class="_"}.
2. {{ member_navigation }}
3. In the table, select the **Action** icon, and then select {{  remove_button  }} or **Remove invitee**.
4. Follow the on-screen instructions to remove the member or invitee.

## Export members

Owners can export a CSV file containing all members.
The CSV file may contain the following fields:

 * **Name**: The user's name.
 * **Username**: The user's Docker ID.
 * **Email**: The user's email address.
 * **Type**: The type of user. For example, **Invitee** for users who have not accepted the organization's invite, or **User** for users who are members of the organization.
 * **Permission**: The user's organization permissions. For example, **Member** or **Owner**.
 * **Teams**: The teams where the user is a member. A team is not listed for invitees.
 * **Date Joined**: The time and date when the user was invited to the organization.
 * **Member of Organizations**: All organizations the user is a member of within a company.
 * **Invited to Organizations**: All organizations the user is an invitee of within a company.
 * **Account Created**: The time and date when the user account was created.

To export a CSV file of the members:

1. Sign in to {{ product_link }}{: target="_blank" rel="noopener" class="_"}.
2. {{ member_navigation }}
3. Select {{ export_button }}.
