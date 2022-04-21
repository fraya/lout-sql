# lout-sql
Lout setup file for SQL program printing

## Install

Copy the files `sql` and `sqlf` in your lout `include` directory. For
instance:

    cp sql* /usr/share/lout/include

## Usage

In your main `.lout` file add:

    @SysInclude { sql }

Later in your document use it:

    @Sql {
        case weekday
	when 1 then return 'monday';
	when 2 then return 'tuesday';
	when 3 then return 'wednesday';
	when 4 then return 'thursday';
	when 5 then return 'friday';
	when 6 then return 'saturday';
	when 7 then return 'sunday';
	else
	  signal sqlstate '45000'
	    set message_text =
	      'Incorrect number of day';
	end case;
    }