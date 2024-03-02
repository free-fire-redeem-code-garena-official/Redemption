<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE html>
<html b:css='false' b:defaultwidgetversion='2' b:layoutsVersion='3' b:responsive='true' b:templateVersion='1.3.0' expr:dir='data:blog.languageDirection' xmlns='http://www.w3.org/1999/xhtml' xmlns:b='http://www.google.com/2005/gml/b' xmlns:data='http://www.google.com/2005/gml/data' xmlns:expr='http://www.google.com/2005/gml/expr'><head>
    <meta content='width=device-width, initial-scale=1' name='viewport'/>
    <title><data:view.title.escaped/></title>
    <b:include data='blog' name='all-head-content'/>
        <meta content='width=device-width, initial-scale=1' name='viewport'/>
        <b:skin version='1.3.0'><![CDATA[
            
               
            
        ]]></b:skin>
        <b:template-skin>
            <![CDATA[
            ]]>
        </b:template-skin>
    </head>
 <body>
  <b:section class='main' id='main' showaddelement='yes'>
    <b:widget id='Header1' locked='false' title='Free fire rewards (Header)' type='Header' visible='true'>
      <b:widget-settings>
        <b:widget-setting name='displayUrl'/>
        <b:widget-setting name='displayHeight'>0</b:widget-setting>
        <b:widget-setting name='sectionWidth'>-1</b:widget-setting>
        <b:widget-setting name='useImage'>false</b:widget-setting>
        <b:widget-setting name='shrinkToFit'>false</b:widget-setting>
        <b:widget-setting name='imagePlacement'>BEHIND</b:widget-setting>
        <b:widget-setting name='displayWidth'>0</b:widget-setting>
      </b:widget-settings>
      <b:includable id='main' var='this'>
    <div class='header-widget'>
      <b:include cond='data:imagePlacement in {&quot;REPLACE&quot;, &quot;BEFORE_DESCRIPTION&quot;}' name='image'/>
      <b:include cond='data:imagePlacement not in {&quot;REPLACE&quot;, &quot;BEFORE_DESCRIPTION&quot;}' name='title'/>
      <b:include cond='data:imagePlacement != &quot;REPLACE&quot;' name='description'/>
    </div>
    <b:include cond='data:imagePlacement == &quot;BEHIND&quot;' name='behindImageStyle'/>
  </b:includable>
      <b:includable id='behindImageStyle'>
    <b:if cond='data:sourceUrl'>
      <b:include cond='data:this.image' data='{                    image: data:this.image,                    selector: &quot;.header-widget&quot;                  }' name='responsiveImageStyle'/>
      <style type='text/css'>
        .header-widget {
          background-position: <data:blog.locale.languageAlignment/>;
          background-repeat: no-repeat;
          background-size: cover;
        }
      </style>
    </b:if>
  </b:includable>
      <b:includable id='description'>
    <p>
      <data:this.description/>
    </p>
  </b:includable>
      <b:includable id='image'>
    <a class='header-image-wrapper' expr:href='data:blog.homepageUrl'>
      <b:include data='{                                                 image: data:image,                                                 altText: data:blog.title.escaped,                                                 originalWidth: data:width,                                                 originalHeight: data:height                                               }' name='responsiveImage'/>
    </a>
  </b:includable>
      <b:includable id='title'>
    <h1>
      <b:tag cond='data:view.url != data:blog.homepageUrl' expr:href='data:blog.homepageUrl' name='a'>
        <data:title/>
      </b:tag>
    </h1>
  </b:includable>
    </b:widget>
    <b:widget id='BlogSearch1' locked='false' title='Search This Blog' type='BlogSearch' visible='true'>
      <b:includable id='main'>
  <b:include name='widget-title'/>
  <b:include name='content'/>
</b:includable>
      <b:includable id='content'>
  <div class='widget-content' role='search'>
    <b:include name='searchForm'/>
  </div>
</b:includable>
      <b:includable id='searchForm'>
  <form expr:action='data:blog.searchUrl'>
    <b:attr cond='not data:view.isPreview' name='target' value='_top'/>
    <b:include name='urlParamsAsFormInput'/>
    <div class='search-input'>
      <input autocomplete='off' expr:aria-label='data:messages.searchThisBlog' expr:placeholder='data:messages.searchThisBlog' expr:value='data:view.isSearch ? data:view.search.query.escaped : &quot;&quot;' name='q'/>
    </div>
    <b:include name='searchSubmit'/>
  </form>
</b:includable>
      <b:includable id='searchSubmit'>
  <input class='search-action' expr:value='data:messages.search.escaped' type='submit'/>
</b:includable>
    </b:widget>
    <b:widget id='AdSense1' locked='false' title='' type='AdSense' visible='true'>
      <b:includable id='main'>
  <div class='widget-content'>
    <b:if cond='data:adCode'>
      <data:adCode/>
    <b:else/>
      <b:include name='defaultAdUnit'/>
    </b:if>
  </div>
</b:includable>
    </b:widget>
    <b:widget id='AdSense2' locked='false' title='' type='AdSense' visible='true'>
      <b:includable id='main'>
  <div class='widget-content'>
    <b:if cond='data:adCode'>
      <data:adCode/>
    <b:else/>
      <b:include name='defaultAdUnit'/>
    </b:if>
  </div>
</b:includable>
    </b:widget>
    <b:widget id='Attribution1' locked='false' title='' type='Attribution' visible='true'>
      <b:widget-settings>
        <b:widget-setting name='copyright'/>
      </b:widget-settings>
      <b:includable id='main' var='this'>
  <div class='widget-content'>
    <div class='blogger'>
      <a expr:href='data:bloggerUrl' rel='nofollow'>
        <b:include name='flatBloggerIcon'/>
        <b:message name='messages.poweredByBlogger'/>
      </a>
    </div>

    <b:if cond='data:imageAuthor'>
      <div class='image-attribution'>
        <b:if cond='data:imageAuthor.url'>
          <b:message name='messages.templateImagesByLink'>
            <b:param expr:value='data:imageAuthor.url'/>
            <b:param expr:value='data:imageAuthor.name'/>
          </b:message>
        <b:else/>
          <b:message name='messages.templateImagesBy'>
            <b:param expr:value='data:imageAuthor.name'/>
          </b:message>
        </b:if>
      </div>
    </b:if>

    <b:if cond='data:copyright != &quot;&quot;'>
      <div class='copyright'><data:copyright/></div>
    </b:if>
  </div>
</b:includable>
    </b:widget>
    <b:widget id='BlogArchive1' locked='false' title='' type='BlogArchive' visible='true'>
      <b:widget-settings>
        <b:widget-setting name='showStyle'>FLAT</b:widget-setting>
        <b:widget-setting name='yearPattern'>yyyy</b:widget-setting>
        <b:widget-setting name='showWeekEnd'>true</b:widget-setting>
        <b:widget-setting name='monthPattern'>MMMM yyyy</b:widget-setting>
        <b:widget-setting name='dayPattern'>MMM dd</b:widget-setting>
        <b:widget-setting name='weekPattern'>MM/dd</b:widget-setting>
        <b:widget-setting name='chronological'>false</b:widget-setting>
        <b:widget-setting name='showPosts'>true</b:widget-setting>
        <b:widget-setting name='frequency'>MONTHLY</b:widget-setting>
      </b:widget-settings>
      <b:includable id='main' var='this'>
  <b:include name='widget-title'/>
  <b:include name='content'/>
</b:includable>
      <b:includable id='content'>
  <div class='widget-content'>
    <div id='ArchiveList'>
      <div expr:id='data:widget.instanceId + &quot;_ArchiveList&quot;'>
        <b:include cond='data:this.style == &quot;HIERARCHY&quot;' name='hierarchy'/>
        <b:include cond='data:this.style in {&quot;FLAT&quot;, &quot;MENU&quot;}' name='flat'/>
      </div>
    </div>
  </div>
</b:includable>
      <b:includable id='flat'>
  <ul class='flat'>
    <b:loop values='data:data' var='i'>
      <li class='archivedate'>
        <a expr:href='data:i.url'>
          <data:i.name/><span class='post-count'><data:i.post-count/></span>
        </a>
      </li>
    </b:loop>
  </ul>
</b:includable>
      <b:includable id='hierarchy'>
  <b:include data='data' name='interval'/>
</b:includable>
      <b:includable id='interval' var='intervals'>
  <ul class='hierarchy'>
    <b:loop values='data:intervals' var='interval'>
      <li class='archivedate'>
        <div class='hierarchy-title'>
          <a class='post-count-link' expr:href='data:interval.url'>
            <data:interval.name/>
            <span class='post-count'><data:interval.post-count/></span>
          </a>
        </div>
        <div class='hierarchy-content'>
          <b:include cond='data:interval.data' data='interval.data' name='interval'/>
          <b:include cond='data:interval.posts' data='interval.posts' name='posts'/>
        </div>
      </li>
    </b:loop>
  </ul>
</b:includable>
      <b:includable id='posts' var='posts'>
  <ul class='posts hierarchy'>
    <b:loop values='data:posts' var='post'>
      <li>
        <a expr:href='data:post.url'><data:post.title/></a>
      </li>
    </b:loop>
  </ul>
</b:includable>
    </b:widget>
    <b:widget id='Label1' locked='false' title='Labels' type='Label' visible='true'>
      <b:widget-settings>
        <b:widget-setting name='sorting'>ALPHA</b:widget-setting>
        <b:widget-setting name='display'>LIST</b:widget-setting>
        <b:widget-setting name='selectedLabelsList'/>
        <b:widget-setting name='showType'>ALL</b:widget-setting>
        <b:widget-setting name='showFreqNumbers'>false</b:widget-setting>
      </b:widget-settings>
      <b:includable id='main' var='this'>
  <b:include name='widget-title'/>
  <b:include name='content'/>
</b:includable>
      <b:includable id='cloud'>
  <b:loop values='data:labels' var='label'>
    <span class='label-size'>
      <b:class expr:name='&quot;label-size-&quot; + data:label.cssSize'/>
      <a class='label-name' expr:href='data:label.url'>
        <data:label.name/>
        <b:if cond='data:this.showFreqNumbers'>
          <span class='label-count'><data:label.count/></span>
        </b:if>
      </a>
    </span>
  </b:loop>
</b:includable>
      <b:includable id='content'>
  <div class='widget-content'>
    <b:class expr:name='data:this.display + &quot;-label-widget-content&quot;'/>
    <b:include cond='data:this.display == &quot;list&quot;' name='list'/>
    <b:include cond='data:this.display == &quot;cloud&quot;' name='cloud'/>
  </div>
</b:includable>
      <b:includable id='list'>
  <ul>
    <b:loop values='data:labels' var='label'>
      <li>
        <a class='label-name' expr:href='data:label.url'>
          <data:label.name/>
          <b:if cond='data:this.showFreqNumbers'>
            <span class='label-count'><data:label.count/></span>
          </b:if>
        </a>
      </li>
    </b:loop>
  </ul>
</b:includable>
    </b:widget>
    <b:widget id='ReportAbuse1' locked='false' title='' type='ReportAbuse' visible='true'>
      <b:includable id='main'>
  <b:include name='reportAbuse'/>
</b:includable>
    </b:widget>
    <b:widget cond='data:view.isSingleItem and data:posts any (p =&gt; p.id != data:view.postId)' id='PopularPosts1' locked='false' title='' type='PopularPosts' visible='true'>
      <b:widget-settings>
        <b:widget-setting name='numItemsToShow'>3</b:widget-setting>
        <b:widget-setting name='showThumbnails'>true</b:widget-setting>
        <b:widget-setting name='showSnippets'>true</b:widget-setting>
        <b:widget-setting name='timeRange'>LAST_YEAR</b:widget-setting>
      </b:widget-settings>
      <b:includable id='main' var='this'>
  <b:include name='widget-title'/>
  <div class='widget-content'>
    <b:include name='snippetedPosts'/>
  </div>
</b:includable>
    </b:widget>
    <b:widget cond='!data:view.isPost' id='PageList1' locked='false' title='' type='PageList' visible='false'>
      <b:widget-settings>
        <b:widget-setting name='pageListJson'><![CDATA[{"home":{"href":"http://free-fire-rewards-xyz.blogspot.com/","position":0,"title":"Home"}}]]></b:widget-setting>
        <b:widget-setting name='homeTitle'>Home</b:widget-setting>
      </b:widget-settings>
      <b:includable id='main'>
  <b:include name='widget-title'/>
  <b:include name='content'/>
</b:includable>
      <b:includable id='content'>
  <div class='widget-content'>
    <b:include name='pageList'/>
  </div>
</b:includable>
      <b:includable id='overflowButton'>
  <b:include name='verticalMoreIcon'/>
</b:includable>
      <b:includable id='overflowablePageList'>
  <div class='overflowable-container'>
    <div class='overflowable-contents'>
      <div class='container'>
        <b:with value='true' var='overflow'>
        <b:with value='&quot;tabs&quot;' var='pageListClass'>
          <b:include name='pageList'/>
        </b:with>
        </b:with>
      </div>
    </div>
    <div class='overflow-button hidden'>
      <b:include name='overflowButton'/>
    </div>
  </div>
</b:includable>
      <b:includable id='pageLink'>
  <li>
    <b:class cond='data:overflow' name='overflowable-item'/>
    <b:class cond='data:link.isCurrentPage' name='selected'/>

    <a expr:href='data:link.href'><data:link.title/></a>
  </li>
</b:includable>
      <b:includable id='pageList'>
  <ul>
    <b:class cond='data:pageListClass' expr:name='data:pageListClass'/>
    <b:loop values='data:links' var='link'>
      <b:include name='pageLink'/>
    </b:loop>
  </ul>
</b:includable>
    </b:widget>
    <b:widget id='Profile1' locked='false' title='About Me' type='Profile' visible='true'>
      <b:widget-settings>
        <b:widget-setting name='showaboutme'>true</b:widget-setting>
        <b:widget-setting name='showlocation'>false</b:widget-setting>
      </b:widget-settings>
      <b:includable id='main' var='this'>
  <b:include name='widget-title'/>
  <b:include name='content'/>
</b:includable>
      <b:includable id='authorProfileImage'>
  <img class='profile-img' expr:alt='data:messages.myPhoto' expr:height='data:authorPhoto.height' expr:src='data:authorPhoto.image' expr:width='data:authorPhoto.width'/>
</b:includable>
      <b:includable id='content'>
  <b:if cond='data:team'>
    <div class='widget-content team'>
      <b:include name='teamProfile'/>
    </div>
  <b:else/>
    <div class='widget-content individual'>
      <b:include name='userProfile'/>
    </div>
  </b:if>
</b:includable>
      <b:includable id='defaultProfileImage'>
  <div class='default-avatar'/>
</b:includable>
      <b:includable id='profileImage'>
  <b:if cond='data:authorPhoto.image'>
    <b:include name='authorProfileImage'/>
  <b:else/>
    <b:include name='defaultProfileImage'/>
  </b:if>
</b:includable>
      <b:includable id='teamProfile'>
  <ul>
    <b:loop values='data:authors' var='author'>
      <li>
        <div class='team-member'>
          <b:include data='author' name='teamProfileLink'/>
        </div>
      </li>
    </b:loop>
  </ul>
</b:includable>
      <b:includable id='teamProfileLink'>
  <a class='profile-link g-profile' expr:href='data:userUrl' rel='nofollow'>
    <b:include name='profileImage'/>
    <span class='profile-name'><data:display-name/></span>
  </a>
</b:includable>
      <b:includable id='userLocation'>
  <dd class='profile-data location'><data:location/></dd>
</b:includable>
      <b:includable id='userProfile'>
  <b:include name='userProfileImage'/>
  <b:include name='userProfileInfo'/>
</b:includable>
      <b:includable id='userProfileData'>
  <dt class='profile-data'>
    <a class='profile-link g-profile' expr:href='data:userUrl' rel='author nofollow'>
      <data:displayname/>
    </a>
  </dt>
</b:includable>
      <b:includable id='userProfileImage'>
  <a expr:href='data:userUrl' rel='nofollow'>
    <b:include name='profileImage'/>
  </a>
</b:includable>
      <b:includable id='userProfileInfo'>
  <div class='profile-info'>
    <dl class='profile-datablock'>
      <b:class cond='data:showlocation and data:location != &quot;&quot;' name='has-location'/>

      <b:include name='userProfileData'/>
      <b:include cond='data:showlocation and data:location != &quot;&quot;' name='userLocation'/>
      <b:include cond='data:aboutme != &quot;&quot;' name='userProfileText'/>
    </dl>
    <b:include name='viewProfileLink'/>
  </div>
</b:includable>
      <b:includable id='userProfileText'>
  <dd class='profile-textblock'>
    <data:aboutme/>
  </dd>
</b:includable>
      <b:includable id='viewProfileLink'>
  <a class='profile-link' expr:href='data:userUrl' rel='author nofollow'>
    <data:messages.viewMyCompleteProfile/>
  </a>
</b:includable>
    </b:widget>
    <b:widget cond='data:view.isHomepage' id='FeaturedPost1' locked='false' title='' type='FeaturedPost' visible='true'>
      <b:widget-settings>
        <b:widget-setting name='showSnippet'>true</b:widget-setting>
        <b:widget-setting name='showPostTitle'>true</b:widget-setting>
        <b:widget-setting name='showFirstImage'>true</b:widget-setting>
        <b:widget-setting name='useMostRecentPost'>true</b:widget-setting>
      </b:widget-settings>
      <b:includable id='main' var='this'>
  <b:include name='widget-title'/>
  <div class='widget-content'>
    <b:include name='snippetedPosts'/>
  </div>
</b:includable>
    </b:widget>
    <b:widget id='Blog1' locked='false' title='Blog Posts' type='Blog' visible='true'>
      <b:widget-settings>
        <b:widget-setting name='showDateHeader'>false</b:widget-setting>
        <b:widget-setting name='style.textcolor'>#ffffff</b:widget-setting>
        <b:widget-setting name='showShareButtons'>true</b:widget-setting>
        <b:widget-setting name='showCommentLink'>true</b:widget-setting>
        <b:widget-setting name='style.urlcolor'>#ffffff</b:widget-setting>
        <b:widget-setting name='showAuthor'>false</b:widget-setting>
        <b:widget-setting name='style.linkcolor'>#ffffff</b:widget-setting>
        <b:widget-setting name='style.unittype'>TextAndImage</b:widget-setting>
        <b:widget-setting name='style.bgcolor'>#ffffff</b:widget-setting>
        <b:widget-setting name='timestampLabel'/>
        <b:widget-setting name='reactionsLabel'/>
        <b:widget-setting name='showAuthorProfile'>false</b:widget-setting>
        <b:widget-setting name='style.layout'>1x1</b:widget-setting>
        <b:widget-setting name='showLabels'>true</b:widget-setting>
        <b:widget-setting name='showLocation'>true</b:widget-setting>
        <b:widget-setting name='postLabelsLabel'/>
        <b:widget-setting name='showTimestamp'>true</b:widget-setting>
        <b:widget-setting name='postsPerAd'>3</b:widget-setting>
        <b:widget-setting name='showBacklinks'>false</b:widget-setting>
        <b:widget-setting name='style.bordercolor'>#ffffff</b:widget-setting>
        <b:widget-setting name='showInlineAds'>true</b:widget-setting>
        <b:widget-setting name='showReactions'>false</b:widget-setting>
      </b:widget-settings>
      <b:includable id='main' var='this'>
  <div class='blog-posts hfeed container'>
    <b:loop index='i' values='data:posts' var='post'>
      <b:include data='post' name='postCommentsAndAd'/>
    </b:loop>
  </div>
  <b:include cond='data:view.isMultipleItems' name='postPagination'/>
  <b:include name='feedLinks'/>
</b:includable>
      <b:includable id='aboutPostAuthor'>
  <div class='author-name'>
    <a class='g-profile' expr:href='data:post.author.profileUrl' rel='author' title='author profile'>
      <span>
        <data:post.author.name/>
      </span>
    </a>
  </div>
  <div>
    <span class='author-desc'>
      <data:post.author.aboutMe/>
    </span>
  </div>
</b:includable>
      <b:includable id='addComments'>
  <a expr:href='data:post.commentsUrl' expr:onclick='data:post.commentsUrlOnclick'>
    <b:message name='messages.postAComment'/>
  </a>
</b:includable>
      <b:includable id='commentAuthorAvatar'>
  <div class='avatar-image-container'>
    <img class='author-avatar' expr:src='data:comment.authorAvatarSrc' height='35' width='35'/>
  </div>
</b:includable>
      <b:includable id='commentDeleteIcon' var='comment'>
  <span expr:class='&quot;item-control &quot; + data:comment.adminClass'>
    <b:if cond='data:showCmtPopup'>
      <div class='goog-toggle-button'>
        <div class='goog-inline-block comment-action-icon'/>
      </div>
    <b:els# Redemption
