## Feedback

Wow, I'm amazed that you had exact agreement all the way down the line with my numbers. I think you're the first person 
for whom that is true. 

Make use of more markdown cells in your notebooks to tell us what's going on. It makes the code a bit easier to read.

The header/no header lists work fine, but it's not very sustainable. Imagine you had 500 files instead of 50 and think about
which parts of your code would still work. Ideally it'd be nice to have code that scaled as the number of files grew. 

I'm not sure what the way is to avoid `x`, but I agree with you there's probably a way to map those functions across all columns. I mean, 
check out `map` and see if that's a Pandas thing. 

Same thing on sustainability for all the cells you have that look like 
```
wedge_dict['transArchive_201504_201506'].to_gbq(destination_table= 'Wedge.transArchive_201504_201506',
                                               chunksize= 500000,
                                               project_id= gbq_proj_id,
                                               if_exists='replace')
                                               
```

Is there any reason you can't just iterate over the keys and do all of that? As an aside, it appears to me that you have
everything read into memory at once. That's another piece that isn't super sustainable, since it'd be easy to have a terabyte
of data you needed to process this way. 

But, boy, you really have the patience of Job. 

For Task 2, how big was your output file? I'm confused by the massive download status bar thing. I think there's a good chance that `Sample_owner_list` has
more owners than you intend for it to have. Confirm that number for me before we call this complete, but you can just do that over Teams. Also, try
not to mix cases in these names. Just go with `sample_owner_list`. Otherwise the errors will drive you nuts. 

For Task 3, do all your imports at the top of your code. There are some potentially easier ways to do the stuff you do, but this looks
like it works. 



