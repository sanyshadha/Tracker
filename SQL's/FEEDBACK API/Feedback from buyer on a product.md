```SQL
select
f.fdbk_id as "feedbackId",
f.spares_user_id as "sparesUserId",
su.user_email as "email",
f.ref_id as "referenceId",
f.rating as "rating",
f.rvw_txt as "comments",
fm.media_url as "media",
f.fdbk_dt as "feedbackDate",
avg(f.rating) as "averageRating"
from spares.feedback f
join spares.spares_users su on su.spares_user_id = f.spares_user_id
left join spares.feedback_media fm on fm.fdbk_id = f.fdbk_id
where f.fdbk_id = 14
group by f.fdbk_id, f.spares_user_id, su.user_email, f.ref_id, f.rating, f.rvw_txt, fm.media_url, f.fdbk_dt
```

