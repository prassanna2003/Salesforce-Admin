creating a Salesforce CRM team with a team lead and three team members

```apex
// Set the time zone to India Standard Time
TimeZone tz = TimeZone.getTimeZone('Asia/Kolkata');
DateTime now = DateTime.now(tz);

// Create a team lead
User teamLead = new User(
    FirstName = 'Prasana',
    LastName = 'Venkatesh',
    Alias = 'pvenkatesh',
    Email = 'pvenkatesh@salesforce.com',
    Username = 'pvenkatesh@salesforce.com',
    CommunityNickname = 'pvenkatesh',
    TimeZoneSidKey = 'Asia/Kolkata',
    LocaleSidKey = 'en_US',
    EmailEncodingKey = 'UTF-8',
    LanguageLocaleKey = 'en_US'
);
insert teamLead;

// Create team members
User teamMember1 = new User(
    FirstName = 'Manikandan',
    LastName = 'B',
    Alias = 'mb',
    Email = 'mb@salesforce.com',
    Username = 'mb@salesforce.com',
    CommunityNickname = 'mb',
    TimeZoneSidKey = 'Asia/Kolkata',
    LocaleSidKey = 'en_US',
    EmailEncodingKey = 'UTF-8',
    LanguageLocaleKey = 'en_US'
);
insert teamMember1;

User teamMember2 = new User(
    FirstName = 'Pemeena',
    LastName = '',
    Alias = 'pemeena',
    Email = 'pemeena@salesforce.com',
    Username = 'pemeena@salesforce.com',
    CommunityNickname = 'pemeena',
    TimeZoneSidKey = 'Asia/Kolkata',
    LocaleSidKey = 'en_US',
    EmailEncodingKey = 'UTF-8',
    LanguageLocaleKey = 'en_US'
);
insert teamMember2;

User teamMember3 = new User(
    FirstName = '',
    LastName = '',
    Alias = 'epsi368123',
    Email = 'epsi368123@salesforce.com',
    Username = 'epsi368123@salesforce.com',
    CommunityNickname = 'epsi368123',
    TimeZoneSidKey = 'Asia/Kolkata',
    LocaleSidKey = 'en_US',
    EmailEncodingKey = 'UTF-8',
    LanguageLocaleKey = 'en_US'
);
insert teamMember3;

// Create a team
Group team = new Group(
    Name = 'Salesforce CRM Team',
    Type = 'Regular',
    OwnerId = teamLead.Id
);
insert team;

// Add team members to the team
GroupMember teamMember1Membership = new GroupMember(
    GroupId = team.Id,
    UserOrGroupId = teamMember1.Id
);
insert teamMember1Membership;

GroupMember teamMember2Membership = new GroupMember(
    GroupId = team.Id,
    UserOrGroupId = teamMember2.Id
);
insert teamMember2Membership;

GroupMember teamMember3Membership = new GroupMember(
    GroupId = team.Id,
    UserOrGroupId = teamMember3.Id
);
insert teamMember3Membership;
