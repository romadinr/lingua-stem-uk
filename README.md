# lingua-stem-uk
Perl5 -  Stemming for Ukrainian Language


Lingua::Stem::Uk - Porter's stemming algorithm for Ukrainian

SYNOPSIS

    use Lingua::Stem::Uk;
    my $stems = Lingua::Stem::Uk::stem({ -words => $word_list_reference,
                                         -locale => 'uk',
                                         -exceptions => $exceptions_hash,
                                      });

    my $stem = Lingua::Stem::Uk::stem_word( $word );

DESCRIPTION

This module applies the Porter Stemming Algorithm to its parameters,
returning the stemmed words.

The code is carefully crafted to work in conjunction with the L<Lingua::Stem>
module by Benjamin Franz. This stemmer is also based 
on the work of Aldo Capini, see L<Lingua::Stem::It>, and Aleksandr Guidrevitch, see L<Lingua::Stem::Ru> .

METHODS



stem({ -words => \@words, -locale => 'uk', -exceptions => \%exceptions });

Stems a list of passed words. Returns an anonymous list reference to the stemmed
words.

Example:

  my $stemmed_words = Lingua::Stem::Uk::stem({ -words => \@words,
                                              -locale => 'uk',
                                          -exceptions => \%exceptions,
                          });

stem_word( $word );

Stems a single word and returns the stem directly.

Example:

  my $stem = Lingua::Stem::Uk::stem_word( $word );

stem_caching({ -level => 0|1|2 });

Sets the level of stem caching.

'0' means 'no caching'. This is the default level.

'1' means 'cache per run'. This caches stemming results during a single
    call to 'stem'.

'2' means 'cache indefinitely'. This caches stemming results until
    either the process exits or the 'clear_stem_cache' method is called.

clear_stem_cache;

Clears the cache of stemmed words



0.01 (2017-10-12)

AUTHOR

Roman Romadin <romadinr@i.ua>

SEE ALSO

 Lingua::Stem

COPYRIGHT

Copyright (C) 2003 by Aldo Calpini <dada@perl.it>

Copyright (C) 2004 by Aleksandr Guidrevitch <pillgrim@mail.ru>

Copyright (C) 2017 by Roman Romadin <romadinr@i.ua>

This software may be freely copied and distributed under the same
terms and conditions as Perl itself, either Perl version 5.8.3
or, at your option, any later version of Perl 5 you may
have available..

