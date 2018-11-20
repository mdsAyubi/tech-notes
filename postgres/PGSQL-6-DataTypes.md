# Data Types

Some common data types supported by PostgresSQL. Data types allow us to control the type of data per column basis

## Types

### Numeric

1. `smallint` - 16 bits wide whole numbers. 2^15 for signed numbers.
2. `int` - 32 bits wide whole numbers. 2^31 for signed numbers.
3. `bigint` - 64 bits whole numbers. 2^63 for signed numbers. Around 18Exabytes.
4. `numeric[(precision, scale)]` where
   - `precision` is number of significant figures
   - `scale` is number of values to the right of the decimal point.  
     `numeric` sans precision or scale supports up to 1000 digits of precision.
5. `real` - 32 bits - variable - 6 decimal digits of precision.
6. `double` - 64 bits - variable - 15 digits of precision.
7. `serial` - 32 bits - auto incrementing, 2^31 for signed.
8. `bigserial` - 64 bits - auto incrementing, 2^63 for signed.

### Money

1. `money` - 64 bits - 2^63 for signed.

### Strings

1. `text` - varchar - unlimited - preferred character storage type withing PostgresSQL.
2. `char(n)` - fixed length, blank padded if values is < 'n' length.  
   char(n) truncates the values that are > 'n' length.  
   `char -> char(1)` - effectively becomes a 1 -character field.
3. `varchar(n)` - variable length with 'n' limit, if 'n' is present. Does not blank pad.
   `varchar` -> variable length - Does nt blank pad.  
   Use `text` or `varchar` when storing strings. These are the recommended types.

### Dates and Time

Uses Julian Dates in date calculation.

1. `date` - 32 bits. Dates only.
2. `time` - 64 bits. Defaults to time without timezone.
3. `time with time zone` - 96 bits - date and time with time zone - microsecond precision
4. `timestamp with time zone` - 64 bits. Same as above
5. `timestamp without time zone` - 64 bits. Same as above
6. `interval` - 96 bits. Range of time. Microsecond precision

### Boolean

1. `boolean` - 8 bits - True(1)(on) | False(0)(off)

### Geometric Types

1. lines, circles, polygons etc

### Network Address Types

1. `cidr` - 7 or 19 bytes - IPv4 or IPv^ networks
2. `inet` - 7 or 19 bytes - both host and networks
3. `macaddr` - 48 bits

### Others

1. Arrays
2. XML
3. etc....
