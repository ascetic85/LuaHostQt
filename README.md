LuaHostQt
=========

[quick-cocos2d-x][quick] + [Qt][Qt] = LuaHostQt

* Using exist GLView
    * How to embedded CCEGLView into Qwidget/QWindow ?
    * How to send events ?
* Create new GLView
    * How to create Qt/CCEGLView ??

* Create new GLView
   * MainLoop. Complete cocos2d::CCApplicationProtocol / Maybe cocos2d::CCApplication
   * renderWidth. Complete cocos2d::CCEGLViewProtocol  / Maybe cocos2d::CCEGLView

```c++
class GLView : public cocos2d::CCEGLViewProtocol, public QGLWidget
{
// using glew as cocos2d-x using it.
public:

    virtual void    end() = 0;
    virtual bool    isOpenGLReady() = 0;
    virtual void    swapBuffers() = 0;
    virtual void    setIMEKeyboardState(bool bOpen) = 0;
    
};

class Application : public cocos2d::CCApplicationProtocol, public QApplication
{
// main loop..
public:

   virtual void setAnimationInterval(double interval) = 0;
   virtual ccLanguageType getCurrentLanguage() = 0;
   virtual TargetPlatform getTargetPlatform() = 0;
   
   void run();
};

class AppDelegate : public Application
{

};

// GLView w;
// CCDirector->setOpenGLView(&w);
// AppDelegate app;
// app->run();
```

Chinese
====

��Ҫ�����������:
* ��ѭ��
* ��glew ����GL���� 

���ò���ֻص�Ϊcocos2d-x ��һ��Qt ����ֲ��������.


[quick]:https://github.com/dualface/quick-cocos2d-x
[Qt]:http://qt-project.org/

