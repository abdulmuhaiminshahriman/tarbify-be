# Tarbify 1.0

## Project Idea
1. Users can register themselves as members.
2. Later superadmin or other admin can assign other members to be an admin.
3. User can delete their account permanently.
4. User can do a quick-registration on behalf of other members, and later they need to accept the invitation via email.
5. By default, newly registered member poses a beginner level.
6. Only superadmin and admin can change other's level. Supervisor only allowed to change his/her downline.
7. User can upload profile picture while registration.
8. Level of member can only be changed incrementally.
9. Only admin can see the dashboard page which summarise the statistic for each locality.
10. A user should have the status of active or inactive.

## Table Structure
1. User 
   - id (int) {required}
   - name(string) {required}
   - ic(integer) {required}
   - dob (string) {required}
   - email {required}
   - mobile_no {required}
   - address_1 {nullable}
   - address_2 {nullable}
   - verified {nullable}
   - introducer {required}
   - current_sv {required}
   - current_level {required}
   - registration_date {required}
   - status (active {default}, inactive)
   - group_category (belia, pelajar, murid)
   - ipt {nullable}
   - role (admin, member {default})
   - profile_picture {nullable}
    
    
2. Admin
   - id (int) {required}
   - user_id {required} filled by laravel
   - assigned_by {required} filled by laravel
    

3. Invitation - id, invitee_name, invitee_dob, invitee_email, invitee_mobile_no, invitor
4. Beginner - id, user_id, current_sv, date_in, date_out, pic_in, pic_out, reason_out
5. Intermediate - id, user_id, current_sv, date_in, date_out, pic_in, pic_out, reason_out, level_upgraded_by_id
6. Advance - id, user_id, current_sv, date_in, date_out, pic_in, level_upgraded_by_id

