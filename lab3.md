# Lab Report 3 - The Grep Command (Week 5)

The `grep` command, when used by itself in the format `grep <string> <files>`, is able to search the passed in files for a given string, and it outputs all matching lines. 

However, `grep` offers many different command-line options that add more nuance to the search, four of which are outlined here.

## `-c` : Count of Matching Lines
`grep -c <string> <files>` prints the number of matching lines for each file, rather than printing the matching lines themselves.

**Example 1:**
```
$ grep -c "hijack" technical/911report/*.txt
technical/911report/chapter-1.txt:127
technical/911report/chapter-10.txt:1
technical/911report/chapter-11.txt:20
technical/911report/chapter-12.txt:11
technical/911report/chapter-13.1.txt:1
technical/911report/chapter-13.2.txt:48
technical/911report/chapter-13.3.txt:11
technical/911report/chapter-13.4.txt:52
technical/911report/chapter-13.5.txt:61
technical/911report/chapter-2.txt:0
technical/911report/chapter-3.txt:29
technical/911report/chapter-5.txt:22
technical/911report/chapter-6.txt:0
technical/911report/chapter-7.txt:98
technical/911report/chapter-8.txt:13
technical/911report/chapter-9.txt:6
technical/911report/preface.txt:0
```
- My `grep -c` command here went through all the text files in the `911report` directory, and for each text file, it printed the number of lines where the string `"hijack"` appeared.
- This can reveal some insights about the contents of the files; I can see that `chapter-13.2.txt`, `chapter-13.4.txt`, `chapter-13.5.txt`, and `chapter-7.txt` have the most lines where `"hijack"` appeared, and so I can make a guess that those text files will focus more on the hijacking sequence of events during 9/11 compared to the other text files in the `911report` directory. It would have been much more tedious to do `grep` without the option `-c` and count up all the lines manually or by other commands.

**Example 2:**
```
$ grep -c "climate change" technical/government/Env_Prot_Agen/*.txt
technical/government/Env_Prot_Agen/1-3_meth_901.txt:0
technical/government/Env_Prot_Agen/atx1-6.txt:0
technical/government/Env_Prot_Agen/bill.txt:0
technical/government/Env_Prot_Agen/ctf1-6.txt:0
technical/government/Env_Prot_Agen/ctf7-10.txt:0
technical/government/Env_Prot_Agen/ctm4-10.txt:0
technical/government/Env_Prot_Agen/final.txt:9
technical/government/Env_Prot_Agen/jeffordslieberm.txt:2
technical/government/Env_Prot_Agen/multi102902.txt:0
technical/government/Env_Prot_Agen/nov1.txt:3
technical/government/Env_Prot_Agen/ro_clear_skies_book.txt:0
technical/government/Env_Prot_Agen/section-by-section_summary.txt:0
technical/government/Env_Prot_Agen/tech_adden.txt:0
technical/government/Env_Prot_Agen/tech_sectiong.txt:0
```
- Here, the `grep -c` command went through all the text files in the `government/Env_Prot_Agen` directory, and for each text file, it printed the number of lines where the string `"climate change"` appeared.
- Just like in the previous example, the use of `-c` enables me to quickly see the general premise of the text files by telling me where the topic of *climate change* is talked about. Now I know that I should probably read through the `final.txt` file if I want to read more on the issue of climate change and how the government has responded to it.
 
*Source: I used the `grep --help` command to get a list of all the possible command-line options where I found `-c`.*

## `-i` : Ignore Case
`grep -i <string> <files>` works similarly to the default `grep` command, with the difference that it is not case-sensitive with regards to the string. In other words, it will still consider a line to match the string even if the case isn't the same.

**Example 1:**
```
$ grep -i "neural network" technical/biomed/*.txt
technical/biomed/1471-2105-4-13.txt:        On the other hand, backpropagation neural networks are a
technical/biomed/1471-2105-4-13.txt:        follows from the first. Not only are neural networks
technical/biomed/1471-2105-4-13.txt:        the extent that this is true, neural networks should be
technical/biomed/1471-2105-4-13.txt:          We wished to see if the neural network strategy, of
technical/biomed/1471-2105-4-13.txt:          a trained neural network can be numerically
technical/biomed/1471-2105-4-13.txt:          propagation neural networks could do better using the
technical/biomed/1471-2105-4-13.txt:          At this point, the neural networks were doing a
technical/biomed/1471-2105-4-13.txt:        We believe neural networks will be an ideal tool to
technical/biomed/1471-2105-4-13.txt:        less than 5 minutes. Indeed, the trained neural network
technical/biomed/1471-2105-4-13.txt:        input vectors for a neural network. The neural network
technical/biomed/1471-2105-4-13.txt:        Professional II Plus v.5.3.Neural networks were trained on
technical/biomed/1471-2105-4-13.txt:        data. A possible disadvantage of neural networks,
technical/biomed/1471-2105-4-28.txt:          A Genetic Programming Neural Network (GPNN)
technical/biomed/1471-213X-1-15.txt:        overlapping neural network of the brain than to traffic
technical/biomed/1471-213X-1-15.txt:          Neural Network (PNN) analyses to determine which
technical/biomed/1471-213X-1-15.txt:          Probabilistic neural network analysis
technical/biomed/1471-2164-3-13.txt:        program by Neural Networks (SSPNN,
technical/biomed/1471-2164-3-15.txt:          "Neural Network Promoter Prediction" software
technical/biomed/1471-2202-3-14.txt:          the efficiency of these three major neural networks [ 24
technical/biomed/1471-2202-3-14.txt:          specific associations with specific neural networks.
technical/biomed/1471-2202-3-14.txt:        neural networks. This suggests that the ANT is a suitable
technical/biomed/1471-2288-2-4.txt:        on linear combinations of the markers, and neural networks
technical/biomed/1472-6807-2-2.txt:        ANN = artificial neural network
technical/biomed/gb-2001-2-4-research0011.txt:          neural network promoter prediction algorithm [ 13], with
technical/biomed/gb-2002-3-12-research0087.txt:        the application of time-delay neural networks, and in our
technical/biomed/gb-2002-3-12-research0087.txt:          neural network classifier, which is trained to output
technical/biomed/gb-2002-3-12-research0087.txt:          sequence, and the neural network score as well as the
technical/biomed/gb-2003-4-5-r32.txt:          a simple neural network model and used to classify
technical/biomed/gb-2003-4-5-r32.txt:          vector element before comparison with the neural network.
```
- Here, the `grep -i` command went through all the text files in the `biomed` directory and printed the matching lines where the string `"neural network"` was found. However, notice that lines where `"neural network"` was capitalized to `"Neural Network"` or `"Neural network"` were also included in the output. 
- This is useful, since now I don't have to `grep` for all possible case permutations of the string `"neural network"`. I will now be able to see where `"neural network"` appears even if it is capitalized, such as it is capitalized in `"Genetic Programming Neural Network (GPNN)"`, which normally would have been missed by the default `grep` command.

**Example 2:**
```
$ grep -i "bioinformatics" technical/biomed/*.txt
technical/biomed/1471-2091-3-14.txt:        interpretation, Bioinformatics, literature searches and
technical/biomed/1471-2105-2-9.txt:        The FastGroup program is a first generation bioinformatics
technical/biomed/1471-2105-3-28.txt:          http://bioinformatics.musc.edu/resources.html.
technical/biomed/1471-2105-3-6.txt:          http://bioinformatics.musc.edu/~jonas/usm/.
technical/biomed/1471-2105-4-25.txt:          http://bioinformatics.med.ohio-state.edu/GDVTKfor
technical/biomed/1471-2148-2-7.txt:        JEB carried out the bioinformatics research and drafted
technical/biomed/1471-2148-3-4.txt:        and designed the project, assisted with the bioinformatics,
technical/biomed/1471-2164-4-19.txt:        bioinformatics. S.L.S. coordinated the project and provided
technical/biomed/1471-2180-2-38.txt:          Bioinformatics analysis of the Cpn 1054 gene family
technical/biomed/1472-6750-3-6.txt:        bioinformatics, designed probes, and helped with the
technical/biomed/ar297.txt:            (European Bioinformatics Institute, Wellcome Trust
technical/biomed/gb-2001-2-10-research0041.txt:        13]. A recent bioinformatics analysis of labile mRNAs with
technical/biomed/gb-2001-2-4-research0012.txt:          structural, relationships. Just as modern bioinformatics
technical/biomed/gb-2001-2-4-research0012.txt:        be a necessary stage in the evolution of bioinformatics, as
technical/biomed/gb-2001-2-4-research0012.txt:        evolution of functional bioinformatics. Toward this, we
technical/biomed/gb-2002-3-12-research0078.txt:        evolving bioinformatics tools and databases are all making
technical/biomed/gb-2002-3-12-research0081.txt:        a basic understanding of Unix and bioinformatics tools, as
technical/biomed/gb-2002-3-12-research0081.txt:        of the bioPerl bioinformatics programming components [ 27,
technical/biomed/gb-2002-3-12-research0081.txt:        some standardized bioinformatics format (for example, GAME
technical/biomed/gb-2002-3-12-research0081.txt:        formats supported by common bioinformatics tools. We use
technical/biomed/gb-2002-3-12-research0082.txt:        developing bioinformatics tools. Our groups explored the
technical/biomed/gb-2002-3-12-research0082.txt:        using Apollo. The bioinformatics group at Biogen has been
technical/biomed/gb-2002-3-12-research0082.txt:        community in bioinformatics to develop Apollo further. The
technical/biomed/gb-2002-3-12-research0083.txt:            [ 82]. Data were filtered using the Bioinformatics
technical/biomed/gb-2002-3-12-research0085.txt:          the pipeline were filtered using the Bioinformatics
technical/biomed/gb-2002-3-6-software0001.txt:        to call in bioinformatics experts, and without having to
technical/biomed/gb-2002-3-9-research0043.txt:        nearly comprehensive census and an early bioinformatics
technical/biomed/gb-2002-3-9-research0044.txt:        Our bioinformatics and experimental strategy involved
technical/biomed/gb-2002-3-9-research0044.txt:        Our bioinformatics approach identified 217 candidate
technical/biomed/gb-2002-3-9-research0044.txt:        by orientation-specific RT-PCR supports our bioinformatics
technical/biomed/gb-2002-3-9-research0046.txt:          More recently, the European Bioinformatics Institute
technical/biomed/gb-2003-4-1-r7.txt:          European Bioinformatics Institute [ 24] for human genes,
technical/biomed/gb-2003-4-4-r26.txt:        bioinformatics approaches (such as clustering, functional
technical/biomed/gb-2003-4-4-r26.txt:        where bioinformatics analysis of available ESTs can improve
technical/biomed/gb-2003-4-6-r39.txt:        bioinformatics approach based on EST sequences is an
```
- Again, here the `grep -i` command went through the text files of the `biomed` directory and found all the lines that matched the term `"bioinformatics"`, without being case-sensitive.
- The utility again shows here, since when I'm doing `grep`, there might be instances in the files where `"bioinformatics"` is capitalized, and if I want to be able to catch those lines, then `-i` makes things very straightforward. Now I know that there are some text files that discuss the `"European Bioinformatics Institute"`, which I wouldn't have been able to catch if I just did `grep "bioinformatics" technical/biomed/*.txt"`

*Source: I used the `grep --help` command to get a list of all the possible command-line options where I found `-i`.*

## `-n` : Print Line Numbers
`grep -n <string> <files>` does the exact same things as the default `grep`, but it also prints out the line numbers where the matching lines are found.

**Example 1:**
```
$ grep -n "terrorist organization" technical/911report/*.txt
technical/911report/chapter-10.txt:144:                terrorist organization and that it had obtained new leads helpful to the
technical/911report/chapter-10.txt:244:                international terrorist organizations in the Middle East.
technical/911report/chapter-12.txt:76:                opposed by Islamist terrorist organizations, both inside Muslim countries and in
technical/911report/chapter-12.txt:207:                terrorist organizations have fled to some of the least governed, most lawless places
technical/911report/chapter-13.1.txt:190:                    transnational terrorist organizations with global reach. It should develop net
technical/911report/chapter-13.3.txt:1385:                designated a "foreign terrorist organization" also brings sanctions and stigmatizes
technical/911report/chapter-13.5.txt:3129:                transnational terrorist organizations: their people, goals, strategies,
technical/911report/chapter-13.5.txt:3148:            In our proposal, that reservoir of institutional memory about terrorist organizations
technical/911report/chapter-2.txt:437:                or representatives of terrorist organizations that were still independent. In
technical/911report/chapter-2.txt:605:                pressed it to stop providing a haven for terrorist organizations. Other governments
technical/911report/chapter-3.txt:476:                in response to a spate of incidents involving domestic terrorist organizations. This
technical/911report/chapter-3.txt:717:                including those of terrorist organizations.
technical/911report/chapter-3.txt:2315:                designate the regime as a foreign terrorist organization (thereby avoiding the issue
technical/911report/chapter-3.txt:2402:                about any other top tier terrorist organization."
technical/911report/chapter-5.txt:204:                Sungkar's newly formed terrorist organization, the JI.
technical/911report/chapter-5.txt:363:                comparable terrorist organization, he gives no indication of what other groups he
technical/911report/chapter-5.txt:1004:                a terrorist organization as far-flung as al Qaeda. The story of the plot includes
technical/911report/chapter-6.txt:390:                crackdown on foreign terrorist organizations in the United States. Third,
technical/911report/chapter-6.txt:512:                crack down on terrorist organizations and curtail their fund-raising. The embassy
technical/911report/chapter-6.txt:529:                terrorist organization," it became the duty of U.S. banks to block its transactions
technical/911report/chapter-6.txt:1162:                organizations and a lethal core terrorist organization-to Vice President-elect
technical/911report/chapter-6.txt:1393:                other terrorist organizations."
technical/911report/chapter-7.txt:965:                contacts with Iran and the Iranian-supported worldwide terrorist organization
technical/911report/chapter-8.txt:880:                associated with a terrorist organization to constitute a "foreign power" for
technical/911report/preface.txt:20:                and border control, the flow of assets to terrorist organizations, commercial
```
- Here, the `grep -n` command finds all the matching lines of the text files in the `911report` directory where the phrase `"terrorist organization"` is found. However, on top of the default output, it also prints out the line number of those matching lines (the numbers can be found after the file paths).
- This is useful if I want check the text files directly and quickly find the exact parts of the text where my desired phrase is found, by using the line numbers. 

**Example 2:**
```
$ grep -n "stem cell" technical/biomed/*.txt
technical/biomed/1471-213X-1-1.txt:281:        Other sites of expression correspond to stem cell
technical/biomed/1471-213X-1-10.txt:473:            Culture and selection of embryonic stem cell
technical/biomed/1471-213X-1-11.txt:74:        layer, where stem cells reside, to the outermost layers,
technical/biomed/1471-213X-1-11.txt:97:          basal or stem cells. Parabasal layer (
technical/biomed/1471-213X-1-12.txt:19:        embryonic stem cells [ 13] and bovine somatic cells [ 14]
technical/biomed/1471-213X-2-8.txt:9:        embryonic stem cells. Of the factors that contribute to
technical/biomed/1471-213X-2-8.txt:159:        in the role of Wnts as stem cell growth factors, such as in
technical/biomed/1471-213X-2-8.txt:198:        promote stem cell fate and inhibit cellular
technical/biomed/1471-2164-4-22.txt:55:        stages of spermatogenesis from the gonocyte stem cells to
technical/biomed/1471-2210-2-4.txt:24:        hematopoietic stem cell population has been identified.
technical/biomed/1471-2210-2-4.txt:99:        isolate human hematopoietic stem cells based on the
technical/biomed/1471-2210-2-4.txt:109:        stem cells. The stem cell population must be exquisitely
technical/biomed/1471-2210-2-4.txt:159:        stem cells are characterized by high expression of ALDH1A1,
technical/biomed/1471-2210-2-4.txt:162:        hematopoietic stem cells. Our long-term goal is to use DPAB
technical/biomed/1471-2210-2-4.txt:276:        stem cells, and the subsequent maintenance of the
technical/biomed/1471-2210-2-4.txt:277:        self-renewal capacity of the hematopoietic stem cells, is
technical/biomed/1471-2210-2-4.txt:282:        stem cell assay system. We are attempting to assess the
technical/biomed/1471-2210-2-4.txt:284:        cultured, mouse hematopoietic stem cells.
technical/biomed/1471-230X-1-10.txt:401:        altered programming of ileal stem cells and transit cells
technical/biomed/1471-2407-2-12.txt:109:          transplantation (BMT) or peripheral stem cell
technical/biomed/1471-2407-2-12.txt:298:        population of leukemic stem cells in S-phase over that
technical/biomed/1471-2407-2-15.txt:34:        18 ] . In-vitro, PTEN-/- embryonic stem cells and
technical/biomed/1471-2474-2-2.txt:53:        osteogenic stem cells available for skeletal repair in
technical/biomed/1471-2474-2-2.txt:371:        number of osteogenic stem cells available for skeletal
technical/biomed/1472-6874-2-8.txt:23:        stem cell factor) are encoded at the white spotting (W) and
technical/biomed/1472-6890-1-4.txt:618:          stem cells and subsequent shift of cells between the
technical/biomed/1477-7827-1-36.txt:97:        Villous CT cells are a type of stem cell which divides
technical/biomed/1477-7827-1-46.txt:635:        staining was detected in stem cells and most differentiated
technical/biomed/ar130.txt:23:          Since stem cells are present in both the bone marrow
technical/biomed/ar130.txt:138:        designation as stem cells [ 3].
technical/biomed/ar130.txt:155:        interaction of reconstituted human hematopoietic stem cells
technical/biomed/ar130.txt:612:          because both monocytes and stem cells (and/or
technical/biomed/ar130.txt:648:        differentiation are features of stem cells [ 14, 15]. The
technical/biomed/ar309.txt:8:        development of hematopoietic stem cells and decreases the
technical/biomed/ar745.txt:440:        chondrocytes or stem cells involved in repairing the
technical/biomed/bcr285.txt:496:        because of the higher number of ductal stem cells that
technical/biomed/cvm-2-6-278.txt:219:          humans. Recent advances in stem cell research provide the
technical/biomed/gb-2001-2-11-research0045.txt:408:          As plants contain chloroplasts in leaf and stem cells
technical/biomed/gb-2002-3-5-research0025.txt:317:          meristem cells, undifferentiated stem cells that produce
technical/biomed/gb-2003-4-7-r46.txt:279:          to regulate self-renewal in stem cells and cancer cells,
technical/biomed/gb-2003-4-7-r46.txt:280:          and as tumors may include stem cells [ 9 ] . The entire
```
- Here, the `grep -n` command went through all the text files of the `biomed` directory and printed the matching lines to the phrase `"stem cells"`, as well as including the line numbers of those matching lines.
- Again, what's great here is that if I now want to look into one of these text files and read more into the section involving stem cells, I can simply go directly to the line number instead of having to manually look for the phrase "stem cells." 
*Source: I used the `grep --help` command to get a list of all the possible command-line options where I found `-n`.*

## `-l` : Names of Matching Files
`grep -l <string> <files>` will only print the names of files that have matching lines rather than actually printing all of the matching lines of those files.

**Example 1:**
```
$ grep -l "cancer treatment"  technical/biomed/*.txt
technical/biomed/1471-2164-3-16.txt
technical/biomed/1471-2407-2-3.txt
technical/biomed/1471-2407-2-31.txt
technical/biomed/1471-2407-3-5.txt
technical/biomed/1471-2431-2-1.txt
technical/biomed/1472-6769-1-4.txt
```
- Here, the `grep -l` command looks through all the text files of the `biomed` directory, and only prints the paths of files that had lines matching to `"cancer treatment"`.
- This is very useful because it simplifies the output for me compared to the default `grep` command. If I want to just know the files that discuss cancer treatment, rather than knowing what the matching lines are, I can do just that with `grep -l`. Furthermore, it's very easy to see that 6 unique files talk about cancer treatment, whereas for the default `grep` command, I might see the same file name appear more than once, and thus it would be harder to count how many unique files there are.

**Example 2:**
```
$ grep -l "carbon dioxide" technical/government/Env_Prot_Agen/*.txt
technical/government/Env_Prot_Agen/bill.txt
technical/government/Env_Prot_Agen/jeffordslieberm.txt
technical/government/Env_Prot_Agen/ro_clear_skies_book.txt
technical/government/Env_Prot_Agen/section-by-section_summary.txt
```
- Here, the `grep -l` command goes through all the text files of the `government/Env_Prot_Agen` directory, printing the file names that had lines matching to `"carbon dioxide"`. 
- Again, this provides the same utility as in the prior example. If I just wanted to know which files contained information about carbon dioxide, I get a to-the-point output that describes just that, rather than a whole clutter of matching lines.  
*Source: I used the `grep --help` command to get a list of all the possible command-line options where I found `-l`.*
