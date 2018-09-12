CREATE DATABASE lab1


  CREATE table users(
    id serial constraint,
    firstname varchar(50) not null,
    surname varchar(50) not null
  );



ALTER table  users
    add column "isadmin" INTEGER

INSERT INTO users (firstname, surname, isadmin) VALUES ('Ablai', 'Nuraliev', '1');

select * from users;

ALTER TABLE users ALTER COLUMN isadmin DROP DEFAULT;
ALTER TABLE users ALTER isadmin TYPE bool USING
  CASE
    WHEN isadmin=0 THEN FALSE
    ELSE TRUE
  END;
ALTER TABLE users ALTER COLUMN isadmin SET DEFAULT FALSE;

select  * from users;

ALTER TABLE users
  ADD constraint cons PRIMARY KEY(id)

CREATE table tasks(
    id serial NOT NULL,
    name varchar(50) not null,
    user_id integer default 10000
  );

drop table tasks;
drop database lab1;