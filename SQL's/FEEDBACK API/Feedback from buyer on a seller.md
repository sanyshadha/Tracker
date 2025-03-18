```SQL
SELECT  
f.fdbk_id AS "feedbackId", 
f.spares_user_id AS "sparesUserId", 
su.user_email AS email,  
f.ref_id AS "referenceId", 
f.rating AS "rating", 
f.rvw_txt AS "comments", 
fm.media_url AS media, 
f.fdbk_dt AS "feedbackDate", 
AVG(f.rating) AS ratings 
FROM spares.feedback f 
JOIN spares.spares_users su ON su.spares_user_id = f.spares_user_id 
left JOIN spares.feedback_media fm ON f.fdbk_id = fm.fdbk_id 
GROUP BY f.fdbk_id, f.spares_user_id, su.user_email, f.ref_id, f.rating, f.rvw_txt, fm.media_url, f.fdbk_dt
```
