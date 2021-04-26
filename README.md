READ ME

При издработка е искористен и слeдниот поглед

create or replace view top3_giveaways as
select id, creator_username, count(gp) from giveaway g left join giveaway_participants gp on g.id = gp.giveaway_id
WHERE Cast(g.status as varchar) like CAST('ACTIVE' as varchar)
group by id, creator_username order by count(gp) desc ;
